<! DOCTYPE html >
< html  lang = " en " >
< cabeça >
    < meta  charset = " UTF-8 " >
    < meta  http-equiv = " X-UA-Compatible " content = " IE = edge " >
    < meta  name = " viewport " content = " width = device-width, initial-scale = 1.0 " >
    < title > Bem Vindo </ title >
    < link  rel = " stylesheet " href = " https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css " Integrity = " sha384-B0vP5xmATw1 + K9KRQjQERJvTumQW0nPEUqvOUF6Lp + JQqqvF6Lp3Jouq2FUF6Lp / ZnPqUq2F6Lp / ZnPqUq2F6lC " crossorigin =" anônimo " >
</ head >
<? php

function  _group_by ( $ array , $ key ) {
    $ return = array ();
    foreach ( $ array  as  $ val ) {
        $ return [ $ val -> $ key ] [] = $ val ;
    }
    return  $ return ;
}

$ url = "https://thiago.app/api/posts.php" ;
 
$ ch = curl_init ( $ url );
curl_setopt ( $ ch , CURLOPT_RETURNTRANSFER , true );
curl_setopt ( $ ch , CURLOPT_SSL_VERIFYPEER , false );
$ produtos = json_decode ( curl_exec ( $ ch ));
$ produtosPorCategorias = _grupo_by ( $ produtos , 'categoria' );

?>
< body  style = " background: rgb (2,0,36);
fundo: gradiente linear (180deg, rgba (2,0,36,1) 0%, rgba (9,9,121,1) 35%, rgba (0,212,255,1) 100%); " >
    <? php
        foreach ( $ produtosPorCategorias  as  $ key => $ value ) {
            ?>
            < Br >
            < h2  style = " text-align: center; color: yellow; " >
            <? php
                print_r ( $ key );
            ?>
            </ h2 >
            < section  class = " container " >
        < div  class = " bg-dark p-5 my-5 " style = " border-radius: 10px; box-shadow: 1px 1px 10px black " >
            < div  id = " carouselExampleIndicators_ <? =  $ key  ?> " class = " carrossel slide " data-ride = " carrossel " >
                < ol  class = " indicadores de carrossel pt-5 " >
                    <? php 
                        $ totalIndicadores = count ( $ value ) / 3 ;                        
                        para ( $ i = 0 ; $ i < $ totalIndicadores ; $ i ++) {
                    ?>
                    < li  data-target = " #carouselExampleIndicators_ <? =  $ key  ?> " data-slide-to = " <? =  $ i  ?> " class = " <? php  if ( $ i == 0 ) { echo  'ativo ' ;} ?> " > </ li >
                  <? php } ?>
                </ ol >
                < div  class = " carousel-inner " >
                    <? php                        
                        para ( $ i = 0 ; $ i < contagem ( $ valor );) { ?>
                            < div  class = " carrossel-item <? php  if ( $ i == 0 ) { echo  'ativo' ;} ?> " >
                                < div  class = " row " >
                                    <? php for ( $ j = 0 ; $ j < 3   && $ i < count ( $ value ); $ j ++) { ?>
                                        < div  class = " col-12 col-md-4 my-5 " >
                                        < div  class = " card " style = " largura: 100%; altura: 100%; " >
                                            < img  src = " <? =  $ value [ $ i ] -> imagem  ?> "
                                                classe = " card-img-top " alt = " ... " >
                                            < div  class = " card-body " >
                                                < p  class = " card-text " > <? =  $ value [ $ i ] -> categoria  ?> </ p >
                                                < p  class = " card-text " > <? =  $ value [ $ i ] -> título  ?> </ p >
                                                < p  class = " card-text " style = " text-align: justify; " > <? =  $ value [ $ i ] -> corpo  ?> </ p > 
                                            </ div >
                                        </ div >
                                    </ div >
                                    <? php  $ i ++; } ?>
                                </ div >
                            </ div >
                        
                        <? php 
                        } 
                        ?>

                </ div >   
                < A  class = " carrossel-control-prev " href =" #carouselExampleIndicators_ <? =  $ Chave  ?> "   Papel =" botão " de dados-slide =" prev " >
                < span  class = " carousel-control-prev-icon " aria-hidden = " true " > </ span >
                < span  class = " sr-only " > Anterior </ span >
                </ a >
                < A  class = " carrossel de controle de próxima " href =" #carouselExampleIndicators_ <? =  $ Chave  ?> " Papel =" botão " de dados-slide =" próxima " >
                    < span  class = " carousel-control-next-icon " aria-hidden = " true " > </ span >
                    < span  class = " sr-only " > Próximo </ span >
                </ a >             
            </ div >     
        </ div >
    </ seção >
    <? php
        }

    ?>


< Roteiro  src = " https://code.jquery.com/jquery-3.5.1.slim.min.js " integridade =" SHA384-DfXdz2htPH0lsSSs5nCTpuj / zy4C + OGpamoFVy38MVBnE + IbbVYUew + OrCXaRkfj " crossorigin =" anonymous " > </ script >
< Roteiro  src =" https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js " integridade =" sha384-9 / reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU + 6BZp6G7niu735Sk7lN " crossorigin =" anonymous " > </ script >
< Roteiro  src =" https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/js/bootstrap.min.js " integridade =" sha384- + YQ4JLhjyBLPDQt // I + STsc9iw4uQqACwlvpslubQzn4u2UU2UFM80nGisd026JF " crossorigin =" anonymous " > </ script >
</ body >
</ html >
