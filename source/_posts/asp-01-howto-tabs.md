---
title: asp-01-howto-tabs
date: 2021-06-21 17:27:20
    - asp.net 
    - c#
    - web
    - aspx
categories: 
    - ASP.NET
---

# How To - Tabs (ASP.NET)

Learn how to create tabs width CSS and ASP.NET

## Create Toggleable Tabs
Step 1) Add ASPX:

***Example***
``` html
<body>
    <form id="form1" runat="server">

        <!-- Tab links -->
        <div class="tab">
            <asp:Button 
                ID="btn_1" 
                runat="server" 
                Text="London" 
                CssClass="tab-button tablinks"
                OnCommand="_Click" 
                CommandName="tab" CommandArgument="pnl_1"></asp:Button>

            <asp:Button 
                ID="btn_2" 
                runat="server" 
                Text="Paris" 
                CssClass="tab-button tablinks" 
                OnCommand="_Click" 
                CommandName="tab" 
                CommandArgument="pnl_2"></asp:Button>

            <asp:Button 
            ID="btn_3" 
            runat="server" 
            Text="Tokyo" 
            CssClass="tab-button tablinks" 
            OnCommand="_Click" 
            CommandName="tab" 
            CommandArgument="pnl_3"></asp:Button>
        </div>

        <!-- Tab content -->
        <div runat="server" id="div1">
            <asp:Panel ID="pnl_1" runat="server"
                        CssClass="tabcontent" Visible="false">
                <h3>London</h3>
                <p>London is the capital city of England.</p>
                <asp:TextBox runat="server"></asp:TextBox>
            </asp:Panel>

            <asp:Panel ID="pnl_2" runat="server"
                        CssClass="tabcontent" Visible="false">
                <h3>Paris</h3>
                <p>Paris is the capital of France.</p>
                <asp:TextBox runat="server"></asp:TextBox>
            </asp:Panel>

            <asp:Panel ID="pnl_3" runat="server" 
                        CssClass="tabcontent" Visible="false">
                <h3>Tokyo</h3>
                <p>Tokyo is the capital of Japan.</p>
            </asp:Panel>
        </div>
    </form>
</body>
```


Step 2) Add CSS:    
Style the buttons and the tab content:

***Example***
``` CSS
/* Style the tab */
        .tab {
            overflow: hidden;
            border: 1px solid #ccc;
            background-color: #f1f1f1;
        }

        /* Style the buttons that are used to open the tab content */
        .tab-button {
            background-color: inherit;
            float: left;
            border: none;
            outline: none;
            cursor: pointer;
            padding: 14px 16px;
            transition: 0.3s;
        }

            /* Change background color of buttons on hover */
            .tab-button:hover {
                background-color: #ddd;
            }

            /* Create an active/current tablink class */
            .tab-button.active {
                background-color: #ccc;
            }

        /* Style the tab content */
        .tabcontent {
            /*display: none;*/
            padding: 6px 12px;
            border: 1px solid #ccc;
            border-top: none;
        }
```

Step 3) Add ASPX.cs

***Example***
``` c#
using System.Web.UI.WebControls;

 Button _btn = new Button();
    protected void Page_Load(object sender, EventArgs e)
    {
        if (!IsPostBack) {
            ActivePanel();
        }
    }

    protected void _Click(Object sender, CommandEventArgs e)
    {
        try
        {
            // 이전 버튼
            if (ViewState["old_btn"] != null)
            {
                Button old_btn = (Button)form1.FindControl(ViewState["old_btn"].ToString());
                 old_btn.CssClass = old_btn.CssClass.Replace(" active", "");
            }

            // 현재 버튼
            _btn = (Button)sender;
            _btn.CssClass += " active";

            ViewState["old_btn"] = _btn.ID;


            switch (e.CommandName)
            {
                case "tab":
                    ActivePanel(e.CommandArgument.ToString());
                    break;

                default:
                    break;
            }
        }
        catch (Exception ex)
        {
            // Exception
        }
    }

    protected void ActivePanel(string pnl = "pnl_1")
    {
        if (pnl_1.ID == pnl)
            pnl_1.Visible = true;
        else
            pnl_1.Visible = false;

        if (pnl_2.ID == pnl)
            pnl_2.Visible = true;
        else
            pnl_2.Visible = false;

        if (pnl_3.ID == pnl)
            pnl_3.Visible = true;
        else
            pnl_3.Visible = false;
    }
```

# Reference
[w3schools.com/howto/howto_js_tabs.asp](https://www.w3schools.com/howto/howto_js_tabs.asp)
