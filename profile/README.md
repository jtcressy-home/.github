## Hi there 👋

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
```mermaid
%%{init: {"theme": "neutral", "flowchart": {"rankSpacing": 30, "nodeSpacing": 30, "curve": "basis"}, "securityLevel": "loose"} }%%
flowchart LR
  subgraph terraform-layers [Terraform Layers]
    direction BT
    subgraph repo:vault-config
      direction LR
      layers/vault-deploy ---> layers/vault-config
      
      tf1("<img src='https://github.com/jtcressy-home/vault-config/actions/workflows/terraform.yml/badge.svg'; width='300' />")
    end
    subgraph repo:tailnet-config [Tailnet Config]
      pipeline1(tf)
    end
    subgraph repo:home-udm-config [Home UDM Config]
      pipeline2(tf)
    end
    repo:vault-config --> repo:tailnet-config
    repo:vault-config --> repo:home-udm-config
    %% repo:tailnet-config --> repo:home-udm-config
  end
```
