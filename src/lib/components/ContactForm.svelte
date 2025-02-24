<script>
  import { Form, FormGroup, Label, Input, Button } from 'sveltestrap';
</script>

<Form>
  <FormGroup>
    <Label for="name">Name</Label>
    <Input type="text" id="name" placeholder="Your Name" />
  </FormGroup>
  <FormGroup>
    <Label for="email">Email</Label>
    <Input type="email" id="email" placeholder="Your Email" />
  </FormGroup>
  <FormGroup>
    <Label for="message">Message</Label>
    <Input type="textarea" id="message" placeholder="Your Message" />
  </FormGroup>
  <Button color="primary">Send</Button>
</Form>
