<h1 align="center"> CI / CD para projetos Android usando Github Actions: Pipelines + Workflows </h1>

<p align="center">
  
![workflow_github_actions](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/4784c3d9-cc87-4424-afd8-22d57918c853)

</p>

<h2>Passo a passo:</h2>
<ul>
  <li>Crie o repositório no Github;</li>
  <li>No Android, será criado o workflow para a pipeline de CI CD;</li>
  <li>Coloque o painel lateral do Android no modo Project;</li>
</ul>

![image](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/3cfe3a4b-2fbd-4d4b-91ef-a5ad2c18fd3a)

<ul>
  <li>Clique na raiz do projeto e crie um novo diretório, cujo nome deve ser exatamente como o que vou dizer: <b>.github/workflows;</b></li>
  <li>Agora, precisamos de um arquivo no diretório que acabou de criar, nesse caso, fique à vontade para atribuir o nome, mas a extensão precisa ser ".yml", eu coloquei assim: <b>AndroidBuild.yml;</b></li>
  <li>No Github, na opção Actions, escolha:  <b>set up a workflow yourself;</b> </li>
</ul>

![image](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/c11a9f3f-fc57-42b1-b4de-8a4237256c4b)

<ul>
  <li>Você verá a mesma estrutura que acabou de criar no Android Studio</li>
</ul>

![image](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/80933dba-00f7-4076-9e7c-11e177b9ac5e)

<ul>
  <li>Você pode escolher editar o arquivo no Github ou no Android Studio, no meu caso, eu editei no Android Studio;</li>
  <li>Primeiro, atribuir o nome ao workflow: digite... <b>name: AndroidBuild (coloque o nome do seu workflow);</b></li>
  <li>Agora é necessário definir a condição para o início do workflow digite: <b>on:</b> e clique em ENTER para mudar de linha;</li>
  <li>Em cada pull_request, o workflow será iniciado, então temos que fazer o seguinte: digite... <b>pull_request:</b> e ENTER para mudar de linha de novo;</li>
  <li>Agora vamos definir em qual branch o workflow será iniciado, digite: <b>branches: [ master ].</b> Até aqui estamos dizendo que queremos iniciar este workflow quando alguém acionar um evento
  de pull_request para a branch master.</li>
  <li>Vamos adicionar mais um evento que vai iniciar o workflow também... digite: <b>push:</b>ENTER para mudar de linha;</li>
  <li>De novo, vamos definir a branch master, então: digite: <b>branches: [ master ]. Todo push enviado para a master, vai iniciar o workflow também.</b></li>
  <li>O próximo passo é definir o sistema operacional, que pode ser qualquer um, aqui no exemplo, adicionei o Ubuntu, verão mais atual;</li>
  <li>É preciso adicionar as etapas e, para isso, utilizei o exemplo do Marketplace do Github, como mostra a imagem:</li>
</ul>

![image](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/b88762d6-3677-4a08-9380-886f72d33dc3)

<ul>
  <li>Na barra de buscas, eu busquei pelos itens: Checkout, Setup Java JDK, Upload a Build Artifact</li>
  <li>Algumas alterações são necessárias no build.gradle.kts(:app), faça conforme o que está na imagem:</li>
</ul>

![image](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/ef599c77-c2f7-4dab-85ca-662094768d90)

<ul>
  <li>Ainda precisamos atualizar as informações no item do Setup Java JDK, pois caso contrário, dá erro na hora de executar o job:</li>
  <li>A informação sobre a <a href="https://github.com/marketplace/actions/setup-java-jdk"/>Distribuição do Java</li>
</ul>

![image](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/d4c14a26-0904-4ba1-9866-8d2a5c7dd87a)

<ul>
  <li>O arquivo deve ficar assim no final:</li>
</ul>

![image](https://github.com/DeniseLeandroDeCastro/AndroidCICD/assets/29150094/9cb9af7e-41d5-4195-8832-5832def1a1d6)

<p>Após finalizar o arquivo, precisa commitar as alterações e no Actions colocar o job para executar.</p>



