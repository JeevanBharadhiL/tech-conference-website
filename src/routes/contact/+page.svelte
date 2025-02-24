<script lang="ts">
  import "bootstrap/dist/css/bootstrap.min.css";
  import { Container, Row, Col, Form, FormGroup, Label, Input, Button } from 'sveltestrap';
</script>

<Container class="contact-container py-5">
  <Row class="shadow-lg bg-white rounded p-4">
    <!-- Left: Contact Form -->
    <Col md="7" class="border-end">
      <h2 class="mb-4">Contact Us</h2>
      <Form>
        <Row>
          <Col md="6">
            <FormGroup>
              <Label for="firstName">First Name</Label>
              <Input type="text" id="firstName" placeholder="" />
            </FormGroup>
          </Col>
          <Col md="6">
            <FormGroup>
              <Label for="lastName">Last Name</Label>
              <Input type="text" id="lastName" placeholder="" />
            </FormGroup>
          </Col>
        </Row>
        <Row>
          <Col md="6">
            <FormGroup>
              <Label for="email">Email</Label>
              <Input type="email" id="email" placeholder="" />
            </FormGroup>
          </Col>
          <Col md="6">
            <FormGroup>
              <Label for="phone">Phone Number</Label>
              <Input type="tel" id="phone" placeholder="" />
            </FormGroup>
          </Col>
        </Row>
        <FormGroup>
          <Label for="message">What do you have in mind</Label>
          <Input type="textarea" id="message" placeholder="Please enter query..." />
        </FormGroup>
        <Button class="btn-submit">Submit</Button>
      </Form>
    </Col>
    
    <!-- Right: Contact Details -->
    <Col md="5" class="p-4">
      <h3>Contact us</h3>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim.</p>
      <p>
        <i class="bi bi-telephone me-2"></i> +91 0123456789
      </p>
      <p>
        <i class="bi bi-envelope me-2"></i> hello@workik.com
      </p>
      <p>
        <i class="bi bi-geo-alt me-2"></i> 102 street, y cross 485656
      </p>
      <div class="social-icons mt-3">
        <i class="bi bi-google me-3"></i>
        <i class="bi bi-twitter me-3"></i>
        <i class="bi bi-instagram me-3"></i>
        <i class="bi bi-facebook"></i>
      </div>
    </Col>
  </Row>
</Container>

<style>
  .contact-container {
    max-width: 900px;
    margin: auto;
  }

  .border-end {
    border-right: 1px solid #ddd;
  }

  .btn-submit {
    background-color: #2b3826;
    color: white;
    width: 100px;
  }

  .social-icons i {
    font-size: 20px;
    cursor: pointer;
  }

  .social-icons i:hover {
    color: #2b3826;
  }
</style>
