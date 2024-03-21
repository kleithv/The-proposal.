<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Marriage Proposal</title>
<style>
  body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(to bottom, #ffe6f2, #ffb3d1);
    height: 100vh;
    display: flex;
    color: white ;
    font-size: 24px ;
    justify-content: center;
    align-items: center;
  }
  .proposal-container {
    text-align: center;
  }
  .proposal-btn {
    background-color: #ff007f;
    border: none;
    color: #fff;
    padding: 10px 20px;
    font-size: 18px;
    border-radius: 5px;
    cursor: pointer;
    margin-top: 1px;
    transition: all 0.3s ease;
  }
  .proposal-btn:hover {
    background-color: #ff3399 ;
  }
  #confetti {
    display: none;
    font-size: 24px;
    margin-top: 50px;
    color: #ff3399 ;
  }
</style>
</head>
<body>
 
<div class="proposal-container" id="proposal">
  <h2>Will you marry me?</h2>
  <button id="yes-btn" class="proposal-btn">Yes, of course!!</button>
  <button id="no-btn" class="proposal-btn">No</button>
  <div id="cant-refuse" class="proposal-container" style="display: none;">
    <h2>You can’t refuse.</h2>
    <button id="try-again-btn" class="proposal-btn">Try Again</button>
  </div>
  <div id="confetti">&#127882; We are now officially married. &#127882;</div>
</div>
 
<script>
  let noCount = 0;
 
  document.getElementById('yes-btn').addEventListener('click', function() {
    document.getElementById('yes-btn').style.display = 'none';
    document.getElementById('no-btn').style.display = 'none';
    document.getElementById('confetti').style.display = 'block';
  });
 
  document.getElementById('no-btn').addEventListener('click', function() {
    noCount++;
    if (noCount >= 3) {
      document.getElementById('cant-refuse').style.display = 'block';
      document.getElementById('yes-btn').style.display = 'none';
      document.getElementById('no-btn').style.display = 'none';
    } else {
      document.getElementById('no-btn').style.top = Math.random() * 100 + '%';
      document.getElementById('no-btn').style.left = Math.random() * 100 + '%';
      document.getElementById('no-btn').style.transform = 'scale(' + (1 - noCount * 0.1) + ')';
    }
  });
 
  document.getElementById('try-again-btn').addEventListener('click', function() {
    document.getElementById('yes-btn').style.display = 'block';
    document.getElementById('no-btn').style.display = 'block';
    document.getElementById('confetti').style.display = 'none';
    document.getElementById('cant-refuse').style.display = 'none';
    noCount = 0;
  });
</script>
 
</body>
</html>
