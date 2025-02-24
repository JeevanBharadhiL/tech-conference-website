<script>
  import { Card, CardBody } from 'sveltestrap';
  export let sponsor;
</script>

<Card class="h-100 text-center">
  <CardBody>
    <a href={sponsor.link} target="_blank" rel="noopener noreferrer">
      <img src={sponsor.logo} alt={sponsor.name} class="img-fluid" style="max-height: 100px;" />
    </a>
  </CardBody>
</Card>