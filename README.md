# Домен Контроль ИБ артефактов, зависимостей и образов (T-ADI)

### DEP Контроль использования сторонних компонентов

### Execution

<table>
  <tr>
   <td>Techniques
   </td>
   <td>Description
   </td>
   <td>Mitigation
   </td>
  </tr>
  <tr>
   <td>Modify CI/CD Configuration
   </td>
   <td>Modify CI/CD Configuration on Git Repository
<p>
(CircleCI: .circleci/config.yml, CodeBuild: buildspec.yml, CloudBuild: cloudbuild.yaml, GitHub Actions: .github/workflows/*.yaml)
   </td>
   <td>
<ol>

<li>(Git Repository) Only allow pushing of signed commits

<li>(CI, CD) Disallow CI/CD config modification without review (CI/CD must not follow changes of a branch without review)

<li>(CI, CD) Add signature to CI/CD config and verify it

<li>(CI, CD) Limit egress connections via Proxy and IP restrictions

<li>(CI, CD) Audit Logging of activities

<li>(CI, CD) Security Monitoring using IDS/IPS, and EDR
</li>
</ol>
   </td>
  </tr>
  <tr>
   <td>Inject code to IaC configuration
   </td>
   <td>For example, Terraform allows code execution and file inclusion. The code is executed during CI(plan stage)
<p>
Code Execution: Provider installation(put provider binary with .tf), Use External provider <br>
File inclusion: file Function
   </td>
   <td>
<ol>

<li>(Git Repository) Only allow pushing of signed commits

<li>(CI, CD) Restrict dangerous code through Policy as Code

<li>(CI, CD) Restrict untrusted providers

<li>(CI, CD) Limit egress connections via Proxy and IP restrictions

<li>(CI, CD) Audit Logging of activities

<li>(CI, CD) Security Monitoring using IDS/IPS, and EDR
</li>
</ol>
   </td>
  </tr>
  <tr>
   <td>Inject code to source code
   </td>
   <td>Application executes test code during CI
   </td>
   <td>
<ol>

<li>(CI, CD) Restrict dangerous code through Policy as Code

<li>(CI, CD) Limit egress connections via Proxy and IP restrictions

<li>(CI, CD) Audit Logging of the activities

<li>(CI, CD) Security Monitoring using IDS/IPS, and EDR
</li>
</ol>
   </td>
  </tr>
  <tr>
   <td>Supply Chain Compromise on CI/CD
   </td>
   <td>(Repeated)
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Inject bad dependency
   </td>
   <td>Inject bad dependency
   </td>
   <td>
<ol>

<li>(CI, CD) Code checks by SCA(Software composition analysis)

<li>(CI, CD) Restrict untrusted libraries, and tools

<li>(CI, CD) Limit egress connections via Proxy and IP restrictions

<li>(CI, CD) Audit Logging of activities

<li>(CI, CD) Security Monitoring using IDS/IPS, and EDR
</li>
</ol>
   </td>
  </tr>
  <tr>
   <td>SSH to CI/CD pipelines
   </td>
   <td>Connect to CI/CD pipeline servers via SSH or Valid Token
   </td>
   <td>
<ol>

<li>(CI, CD) Implement strict access control to CI/CD pipeline servers

<li>(CI, CD) Disallow SSH access
</li>
</ol>
   </td>
  </tr>
</table>
