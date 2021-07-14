<? php

namespace  App \ Http \ Controllers ;

use  Illuminate \ Http \ Request ;
use  Illuminate \ Support \ Facades \ Http ;

classe  InitController  estende  controlador
{
    / **
     * Exibir uma lista do recurso.
     *
     * @return \ Illuminate \ Http \ Response
     * /
     índice de função  pública ()
    {
        $ response = Http :: get ( 'https://thiago.app/api/posts.php' );

        $ dados = json_decode ( $ resposta );

        return  view ( 'index' , compact ( 'dados' ));
    }

    / **
     * Mostra o formulário para criação de um novo recurso.
     *
     * @return \ Illuminate \ Http \ Response
     * /
    public  function  create ()
    {
        //
    }

    / **
     * Armazene um recurso recém-criado no armazenamento.
     *
     * @param \ Illuminate \ Http \ Request $ request
     * @return \ Illuminate \ Http \ Response
     * /
     armazenamento de função  pública ( solicitação $ solicitação ) 
    {
        //
    }

    / **
     * Exposição de recurso especificado.
     *
     * @param int $ id
     * @return \ Illuminate \ Http \ Response
     * /
     mostrar função  pública ( $ id )
    {
        //
    }

    / **
     * Mostra o formulário para editar o recurso específico.
     *
     * @param int $ id
     * @return \ Illuminate \ Http \ Response
     * /
     edição de função  pública ( $ id )
    {
        //
    }

    / **
     * Atualização do recurso especificado sem armazenamento.
     *
     * @param \ Illuminate \ Http \ Request $ request
     * @param int $ id
     * @return \ Illuminate \ Http \ Response
     * /
     atualização de função  pública ( solicitação $ request , $ id ) 
    {
        //
    }

    / **
     * Remove o recurso especificado do armazenamento.
     *
     * @param int $ id
     * @return \ Illuminate \ Http \ Response
     * /
     destruir função  pública ( $ id )
    {
        //
    }
}
