<script>
  let step = 1;
</script>

<div class="body">
  <div class="container">
    <div class="title">
      <h2>Sign Up</h2>
      <p>Please, fill in your information.</p>
    </div>
    <div class="cards">
      <!-- E-mail -->
      <div
        class="signup-card level-1"
        class:active={step == 1}
        class:done={step != 1}
      >
        <div class="signup-card_header email">
          <div class="header-title">
            <i class="fa-solid fa-envelope" /> &nbsp;
            <span>E-mail</span>
          </div>
        </div>
        <div class="signup-card_content">
          <input type="text" placeholder="your@email.com" />
        </div>
        <div class="signup-card_footer">
          <button on:click={() => (step = 2)}>
            Next
            <i class="fa-solid fa-arrow-right" />
          </button>
        </div>
      </div>

      <!-- Password -->
      <div
        class="signup-card"
        class:active={step == 2}
        class:done={step == 3}
        class:level-2={step == 1}
      >
        <div class="signup-card_header password">
          <div class="header-title">
            <i class="fa-solid fa-lock" /> &nbsp;
            <span>Password</span>
          </div>
          <button class="back" on:click={() => (step = 1)}>
            <i class="fa-solid fa-arrow-left" />
          </button>
        </div>
        <div class="signup-card_content">
          <input type="password" placeholder="Your password" />
        </div>
        <div class="signup-card_footer">
          <button on:click={() => (step = 3)}>
            Next
            <i class="fa-solid fa-arrow-right" />
          </button>
        </div>
      </div>

      <!-- Confirm password -->
      <div
        class="signup-card"
        class:active={step == 3}
        class:level-2={step == 2}
        class:level-3={step == 1}
      >
        <div class="signup-card_header confirm-password">
          <div class="header-title">
            <i class="fa-solid fa-lock" /> &nbsp;
            <span>Confirm password</span>
          </div>
          <button class="back" on:click={() => (step = 2)}>
            <i class="fa-solid fa-arrow-left" />
          </button>
        </div>
        <div class="signup-card_content">
          <input type="password" placeholder="Confirm your password" />
        </div>
        <div class="signup-card_footer">
          <button>
            Create account
            <i class="fa-solid fa-arrow-right" />
          </button>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
  .body {
    width: 100%;
    height: 100%;
    background: #c2e59c; /* fallback for old browsers */
    background: -webkit-linear-gradient(
      to right,
      #c2e59c,
      #64b3f4
    ); /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(
      to right,
      #c2e59c,
      #64b3f4
    ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  }

  .container {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .title {
    text-align: center;
    color: #fff;
  }

  .cards {
    position: relative;
    width: 350px;
    height: 300px;
  }

  .signup-card {
    background-color: #fff;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16), 0 3px 6px rgba(0, 0, 0, 0.23);
    border-radius: 10px;
    width: 350px;
    overflow: hidden;

    position: absolute;
    left: 0;

    transition: all 0.5s ease-out;
  }

  .signup-card_header {
    padding: 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-weight: bold;
    font-size: 1.3em;
    border-radius: 8px 8px 0 0;
  }

  button.back {
    background-color: transparent;
    border: none;
    padding: 0;
    margin: 0;
    color: inherit;
    cursor: pointer;
  }

  .signup-card_content {
    padding: 20px;
  }

  .signup-card_content input {
    border-radius: 50px;
    width: 100%;
    padding: 10px 20px;
  }

  .signup-card_footer {
    width: 100%;
    display: flex;
    flex-grow: 1;
    justify-content: center;
    overflow: hidden;
  }

  .signup-card_footer button {
    border: none;
    margin-bottom: 0;
    background-color: none;
    width: 100%;
    height: 45px;
    cursor: pointer;
  }

  /* Colors */

  .signup-card_header.email {
    background-color: rgb(216, 247, 198);
    color: rgb(109, 158, 89);
  }

  .signup-card_header.password {
    background-color: rgb(198, 247, 230);
    color: rgb(89, 158, 147);
  }

  .signup-card_header.confirm-password {
    background-color: rgb(198, 232, 247);
    color: rgb(89, 125, 158);
  }

  /* Levels */

  .level-1 {
    z-index: 3;
  }

  .signup-card.level-2 {
    transform: scale(0.93) translate(0px, 20px);
    z-index: 2;
  }

  .signup-card.level-3 {
    transform: scale(0.86) translate(0px, 40px);
    z-index: 1;
  }

  .signup-card.signup-card.active {
    transform: scale(1) translate(0, 0);
    opacity: 1;
    z-index: 3;
  }

  .signup-card.done {
    transform: translate(-100vh);
    opacity: 0;
    z-index: 4;
  }
</style>
