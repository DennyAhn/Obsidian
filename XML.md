
이 시나리오를 완성하기 위해, 백엔드에서 Node.js와 Express를 사용하여 사용자의 반응 시간과 닉네임을 데이터베이스에 저장하고, 프론트엔드에서 이를 표시하는 방법을 개발해야 합니다. 여기서는 간단한 예시로 MongoDB를 사용합니다. 실제 개발 환경에서는 MongoDB Atlas 같은 클라우드 기반 서비스를 사용하거나, 로컬 환경에서 MongoDB를 설정할 수 있습니다.

### 백엔드 수정

1. **모델 설정**: 사용자의 반응 시간과 닉네임을 저장할 모델을 정의합니다.
    
    javascriptCopy code
    
    `const mongoose = require('mongoose'); const reactionTimeSchema = new mongoose.Schema({     nickname: String,     reactionTime: Number }); const ReactionTime = mongoose.model('ReactionTime', reactionTimeSchema);`
    
2. **데이터 저장**: 사용자가 테스트를 완료하고 닉네임을 제출하면, 반응 시간과 함께 데이터베이스에 저장합니다.
    
    javascriptCopy code
    
    `app.post('/submit', async (req, res) => {     const { nickname, reactionTime } = req.body;     const newRecord = new ReactionTime({ nickname, reactionTime });     await newRecord.save();     res.status(200).send('Reaction time recorded.'); });`
    
3. **순위 조회**: 가장 빠른 반응 시간 순으로 상위 5개의 기록을 조회합니다.
    
    javascriptCopy code
    
    `app.get('/rankings', async (req, res) => {     const rankings = await ReactionTime.find({}).sort({ reactionTime: 1 }).limit(5);     res.status(200).json(rankings); });`
    

### 프론트엔드 수정

프론트엔드에는 반응 시간 테스트 결과를 제출하는 폼과 상위 5개의 기록을 보여주는 섹션을 추가합니다.

1. **HTML 추가**:
    
    htmlCopy code
    
    `<div>     <input type="text" id="nickname" placeholder="Enter your nickname">     <button onclick="submitResult()">Submit Result</button> </div> <div id="rankings"></div>`
    
2. **결과 제출 및 순위 표시**:
    
    javascriptCopy code
    
    ``async function submitResult() {     const reactionTime = endTime - startTime;     const nickname = document.getElementById('nickname').value;      await fetch('/submit', {         method: 'POST',         headers: {             'Content-Type': 'application/json',         },         body: JSON.stringify({ nickname, reactionTime }),     });      loadRankings(); }  async function loadRankings() {     const response = await fetch('/rankings');     const rankings = await response.json();     const rankingsElement = document.getElementById('rankings');     rankingsElement.innerHTML = '<h2>Top 5 Rankings</h2>';     rankings.forEach((record, index) => {         rankingsElement.innerHTML += `<p>${index + 1}. ${record.nickname}: ${record.reactionTime} ms</p>`;     }); }  loadRankings(); // 페이지 로드 시 순위를 불러옵니다.``
    

이 코드 조각은 MongoDB와의 연동을 위해 `mongoose`를 사용하는 Node.js 백엔드 서버와, 반응 시간을 기록하고 순위를 표시하는 프론트엔드 로직을 포함합니다. 사용자가 닉네임과 반응 시간을 제출하면 서버는 이를 데이터베이스에 저장하고, 상위 5개의 기록을 프론트엔드에 전송하여 표시합니다.


const mongoose = require('mongoose');
const reactionTimeSchema = new mongoose.Schema({
    nickname: String,
    reactionTime: Number
});
const ReactionTime = mongoose.model('ReactionTime', reactionTimeSchema);

<div id="rankings"></div>





<div>
    <input type="text" id="nickname" placeholder="Enter your nickname">
    <button onclick="submitResult()">Submit Result</button>
</div>
<div id="rankings"></div>
