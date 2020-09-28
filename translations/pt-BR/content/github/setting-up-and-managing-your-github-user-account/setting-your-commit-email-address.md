---
title: Configurar o endereço de e-mail do commit
intro: 'Você pode configurar um endereço de e-mail principal no {{ site.data.variables.product.product_name }} associado às opções do Git baseadas na web executadas, como edições e merges.'
redirect_from:
  - /articles/keeping-your-email-address-private/
  - /articles/setting-your-commit-email-address-on-github/
  - /article/about-commit-email-addresses/
  - /articles/git-email-settings/
  - /articles/setting-your-email-in-git/
  - /articles/set-your-user-name-email-and-github-token/
  - /articles/setting-your-commit-email-address-in-git/
  - /articles/setting-your-commit-email-address
versions:
  free-pro-team: '*'
  enterprise-server: '*'
---

### Sobre os endereços de e-mail do commit

O {{ site.data.variables.product.product_name }} usa o endereço de e-mail do commit para associar commits à conta do {{ site.data.variables.product.product_name }}. Você pode escolher o endereço de e-mail que será associado aos commits cujo push é feito usando a linha de comando e às operações do Git baseadas na web executadas.

Para operações do Git baseadas na web, você pode configurar o endereço de e-mail do commit no {{ site.data.variables.product.product_name }}. Para commits cujo push é feito usando a linha de comando, você pode configurar o endereço de e-mail do commmit no Git.

{% if currentVersion == "free-pro-team@latest" %}Os commits feitos antes da alteração do endereço de e-mail do commit continuarão associados ao endereço de e-mail anterior.{% else %}Depois de alterar o endereço de e-mail do commit no {{ site.data.variables.product.product_name }}, o novo endereço de e-mail ficará visível por padrão em todas as próximas operações do Git baseadas na web. Os commits feitos antes da alteração do endereço de e-mail do commit continuarão associados ao endereço de e-mail anterior.{% endif %}

{% if currentVersion == "free-pro-team@latest" %}

{% note %}

**Observação**: {{ site.data.reusables.user_settings.no-verification-disposable-emails }}

{% endnote %}

{% endif %}

{% if currentVersion == "free-pro-team@latest" %}Se não quiser usar seu endereço de e-mail pessoal, você poderá usar um endereço de e-mail `no-reply` fornecido pelo {{ site.data.variables.product.product_name }} como o endereço de e-mail do commit. Para usar o endereço de e-mail `noreply` para commits cujo push é feito usando a linha de comando, use esse endereço de e-mail ao configurar o endereço de e-mail do commit no Git. Para usar o endereço `noreply` para operações do Git baseadas na web, configure o endereço de e-mail do commit no GitHub e selecione **Keep my email address private** (Manter meu endereço de e-mail privado).

Você também pode optar por bloquear os commits cujo push é feito usando a linha de comando que expõem seu endereço de e-mail pessoal. Para obter mais informações, consulte "[Bloquear pushes de linha de comando que mostrem endereços de e-mail pessoais](/articles/blocking-command-line-pushes-that-expose-your-personal-email-address)".{% endif %}

Para garantir que os commits sejam atribuídos a você e apareçam no gráfico de contribuições, use um endereço de e-mail que tenha [adicionado à conta do GitHub](/articles/adding-an-email-address-to-your-github-account/){% if currentVersion == "free-pro-team@latest" %} ou o endreço de e-mail `noreply` fornecido pelo {{ site.data.variables.product.product_name }} nas configurações do e-mail{% endif %}.

{% if currentVersion == "free-pro-team@latest" %}

{% note %}

**Observação:** se você criou sua conta do {{ site.data.variables.product.product_name }} _depois de_ 18 de julho de 2017, seu endereço de e-mail `no-reply` fornecido pelo {{ site.data.variables.product.product_name }} é um número de ID com sete dígitos e o seu nome de usuário no formato <code><em>ID+nome de usuário</em>@users.noreply.github.com</code>. Se você criou sua conta do {{ site.data.variables.product.product_name }} _antes de_ 18 de julho de 2017, seu endereço de e-mail `no-reply` fornecido pelo {{ site.data.variables.product.product_name }} é o seu nome de usuário no formato <code><em>nome de usuário</em>@users.noreply.github.com</code>. Você pode obter um endereço de e-mail `no-reply` fornecido pelo {{ site.data.variables.product.product_name }} baseado no ID marcando (ou desmarcando e marcando novamente) **Keep my email address private** (Manter meu endereço de e-mail privado) nas configurações do e-mail.

{% endnote %}

Se você usar o endereço de e-mail `noreply` fornecido pelo {{ site.data.variables.product.product_name }} para fazer commits e [alterar seu nome de usuário](/articles/changing-your-github-username), esses commits não estarão associados à sua conta do {{ site.data.variables.product.product_name }}. Isso não se aplica ao usar um endereço `noreply` fornecido pelo {{ site.data.variables.product.product_name }} baseado no ID. Para obter mais informações, consulte "[Alterar seu nome de usuário do {{ site.data.variables.product.prodname_dotcom }}](/articles/changing-your-github-username)".{% endif %}

### Configurar o endereço de e-mail do commit no {{ site.data.variables.product.prodname_dotcom }}

{{ site.data.reusables.files.commit-author-email-options }}

{{ site.data.reusables.user_settings.access_settings }}
{{ site.data.reusables.user_settings.emails }}
{{ site.data.reusables.user_settings.add_and_verify_email }}
{{ site.data.reusables.user_settings.select_primary_email }}{% if currentVersion == "free-pro-team@latest" %}
{{ site.data.reusables.user_settings.keeping_your_email_address_private }}{% endif %}

### Configurar o endereço de e-mail do commit no Git

Você pode usar o comando `git config` para alterar o endereço de e-mail associado aos commits do Git. O novo endereço de e-mail configurado ficará visível em todos os commits cujo push é feito para o {{ site.data.variables.product.product_name }} usando a linha de comando. Os commits feitos antes da alteração do endereço de e-mail do commit continuarão associados ao endereço de e-mail anterior.

#### Configurar o endereço de e-mail para todos os repositórios no computador

{{ site.data.reusables.command_line.open_the_multi_os_terminal }}
2. {{ site.data.reusables.user_settings.set_your_email_address_in_git }}
   ```shell
   $ git config --global user.email "<em>email@example.com</em>"
   ```
3. {{ site.data.reusables.user_settings.confirm_git_email_address_correct }}
   ```shell
   $ git config --global user.email
   <span class="output">email@example.com</span>
   ```
4. {{ site.data.reusables.user_settings.link_email_with_your_account }}

#### Configurar o endereço de e-mail para um repositório específico

O {{ site.data.variables.product.product_name }} usa o endereço de e-mail definido na configuração local do Git para associar os commits cujo push é feito usando a linha de comando à sua conta do {{ site.data.variables.product.product_name }}.

Você pode alterar o endereço de e-mail associado aos commits feitos em um repositório específico. Isso sobrescreverá as definições de configuração global do Git no repositório em questão, mas não afetará nenhum outro repositório.

{{ site.data.reusables.command_line.open_the_multi_os_terminal }}
2. Altere o diretório de trabalho atual para o repositório local no qual deseja configurar o endereço de e-mail associado aos commits do Git.
3. {{ site.data.reusables.user_settings.set_your_email_address_in_git }}
   ```shell
   $ git config user.email "<em>email@example.com</em>"
   ```
4. {{ site.data.reusables.user_settings.confirm_git_email_address_correct }}
   ```shell
   $ git config user.email
   <span class="output">email@example.com</span>
   ```
5. {{ site.data.reusables.user_settings.link_email_with_your_account }}