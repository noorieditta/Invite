<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Wedding Invitation</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background: #f0e6d2;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
  }

  .container {
    position: relative;
    width: 350px;
    max-width: 90%;
  }

  /* Envelope styles */
  .envelope {
    width: 100%;
    height: 400px;
    background-color: #fff;
    border: 4px solid #c3906b;
    border-radius: 15px;
    cursor: pointer;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    position: relative;
    transition: opacity 0.5s ease, transform 0.5s ease;
  }

  /* Flap of the envelope */
  .flap {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 50%;
    background-color: #d2b48c;
    border-bottom: 2px solid #c3906b;
    border-top-left-radius: 15px;
    border-top-right-radius: 15px;
    transform-origin: bottom;
    transition: transform 1s ease;
    z-index: 2;
  }

  /* When clicked, flip the flap */
  .envelope.open .flap {
    transform: rotateX(-180deg);
  }

  /* Invite content hidden initially */
  .invite {
    display: none;
    padding: 20px;
    background-color: #fff8f0;
    border-radius: 15px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    box-sizing: border-box;
    overflow-y: auto;
  }

  /* Show invite when envelope is open */
  .container.show-invite .invite {
    display: block;
  }

  h2 {
    text-align: center;
    color: #c3906b;
  }

  p {
    font-size: 1.1em;
    line-height: 1.4;
  }
</style>
</head>
<body>

<div class="container" id="inviteContainer">
  <!-- Envelope -->
  <div class="envelope" id="envelope">
    <div class="flap" id="flap"></div>
  </div>
  <!-- Invite Content -->
  <div class="invite" id="inviteContent">
    <h2>You're Invited!</h2>
    <p>Join us for our wedding celebration!</p>
    <p><strong>Date:</strong> August 15, 2025</p>
    <p><strong>Location:</strong> 59 Granville St, Dewsbury WF13 2NF</p>
    <p>Time: 5:00 PM - 10:00 PM</p>
    <p>Please RSVP by August 10th. We can't wait to celebrate with you!</p>
  </div>
</div>

<script>
  const envelope = document.getElementById('envelope');
  const container = document.getElementById('inviteContainer');

  envelope.addEventListener('click', () => {
    // Animate flap flip
    envelope.classList.toggle('open');

    // After flip, hide envelope and show invite
    setTimeout(() => {
      envelope.style.display = 'none';
      container.classList.add('show-invite');
    }, 1000); // match CSS transition duration
  });
</script>

</body>
</html>
