<script>

let coins=[];

const cryptoApi=async function(){
  const url='https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=100&page=1&sparkline=false';
  const res=await fetch(url);
  const data=await res.json();

  coins=data;
  
}
cryptoApi()

</script>

<div class="container">

  <div class="row">

    <table class="table table-dark">

      <thead>
        <tr>
          <th>
        Coin Name
          </th>

          <th>Price</th>
        </tr>
      </thead>

<tbody>
  {#each coins as coin}

  <tr>
    
    <td>
      <img src={coin.image} width="30" alt="">
      <h2>{coin.name}</h2>
    </td>

    <td> 
       <span>{coin.current_price} <strong>$</strong> </span>
    </td>

    
  </tr>

  

  {/each}
</tbody>

    </table>


  </div>



</div>