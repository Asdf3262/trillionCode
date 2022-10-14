<template>
  <div ref="contact" class="contact-us">
    <h3>I am interested in getting the benefits of <span>Up Hellas</span></h3>
    <div>
      <form onsubmit="console.log('Submit Successful');">
        <b-container>
          <b-row>
            <b-col xl="6">
              <label for="fullname">Name & Surname</label>
              <input type="text" id="fullname" name="fullname" placeholder="Your full name.." required>
            </b-col>
            <b-col xl="6">
              <label for="email">Email</label>
              <input type="email" id="email" name="email" placeholder="Your email.." pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,4}$" required>
            </b-col>
          </b-row>
          <b-row>
            <b-col xl="6">
              <label for="phone">Phone</label>
              <input type="tel" id="phone" name="phone" placeholder="69xxxxxxxx" pattern="[0-9]{10}" required>
            </b-col>
            <b-col xl="6" class="products">
              <label for="product">Product</label>
              <select id="product" name="product" required>
                <option value="product1">Product1</option>
                <option value="product2">Product2</option>
                <option value="product3">Product3</option>
              </select>
            </b-col>
          </b-row>
          <b-row class="check">
            <input type="checkbox" id="data" name="data" value="Data">
            <label for="data"> Επιθυμώ να χρησιμοποιηθούν τα παραπάνω στοιχεία μου από την Up Hellas, προκειμένου να ενημερωθώ για τα προϊόντα της,
              βάσει και του Γενικού Κανονισμού για την Προστασία Προσοπικών Δεδομένων που ισχύει από 25/5/2018</label>
          </b-row>
          <b-row class="submits">
            <input type="submit" value="SEND US YOUR MESSAGE">
            <span>OR</span>
            <input type="submit" value="SCHEDULE A MEETING">
          </b-row>
        </b-container>

      </form>
    </div>
  </div>
</template>

<style scoped>
  .contact-us {
    padding: 80px 0 60px 0;
    background-color: #00c8ff;
  }
  .contact-us h3 {
    color: #303644;
    font-size: 38px;
    font-weight: bold;
  }
  h3 span {
    color: #f1a024;
  }
  .contact-us .row {
    margin-bottom: 50px;
  }
  form {
    margin-top: 50px;
  }
  label {
    font-weight: bold;
    display: block;
  }
  input, select {
    width: 100%;
  }
  .check input, .check label {
    display: inline-block;
    width: auto;
  }
  .submits input {
    width: auto;
  }
  .container {
    max-width: 800px;
    width: 100%;
  }
  input, select {
    border: 8px solid rgb(48,54,68);
    border-radius: 50px;
    border-top: 2px solid rgb(48,54,68);
    border-right: 2px solid rgb(48,54,68);
    padding: 15px;
    padding-left: 20px;
    padding-right: 20px;
    font-size: 16px;
    font-weight: bold;
    color: rgb(48,54,68);
  }
  .row div:nth-child(2) input, select {
    border: 8px solid rgb(48,54,68);
    border-bottom: 2px solid rgb(48,54,68);
    border-left: 2px solid rgb(48,54,68);
  }
  .check label{
    max-width: 700px;
    font-size: 12px;
    margin-left: 30px;
  }
  .submits input:first-child {
    background-color: #ffce3c;
  }
  .submits span {
    margin: auto 20px auto 20px;
    font-weight: bold;
  }
</style>
