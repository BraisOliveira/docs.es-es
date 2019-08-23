---
title: Procedimiento para deshabilitar fichas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 888228c28dce591b237be16b6a321afee0105208
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967147"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="34ba8-102">Procedimiento para deshabilitar fichas</span><span class="sxs-lookup"><span data-stu-id="34ba8-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="34ba8-103">En algunas ocasiones, deseará restringir el acceso a los datos que están disponibles en la aplicación Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="34ba8-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="34ba8-104">Un ejemplo de esto podría ser cuando se muestran datos en las páginas de fichas de un control de ficha. los administradores pueden tener información en una página de ficha que desea restringir a usuarios de nivel inferior o invitado.</span><span class="sxs-lookup"><span data-stu-id="34ba8-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="34ba8-105">Para deshabilitar las páginas de fichas mediante programación</span><span class="sxs-lookup"><span data-stu-id="34ba8-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="34ba8-106">Escriba código para controlar el evento del control <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> de pestaña.</span><span class="sxs-lookup"><span data-stu-id="34ba8-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="34ba8-107">Este es el evento que se genera cuando el usuario cambia de una pestaña a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="34ba8-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="34ba8-108">Compruebe las credenciales.</span><span class="sxs-lookup"><span data-stu-id="34ba8-108">Check credentials.</span></span> <span data-ttu-id="34ba8-109">En función de la información presentada, puede que desee comprobar el nombre de usuario con el que ha iniciado sesión el usuario o alguna otra forma de credenciales antes de permitir que el usuario vea la ficha.</span><span class="sxs-lookup"><span data-stu-id="34ba8-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="34ba8-110">Si el usuario tiene las credenciales apropiadas, muestre la ficha en la que se hizo clic.</span><span class="sxs-lookup"><span data-stu-id="34ba8-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="34ba8-111">Si el usuario no tiene las credenciales adecuadas, muestre un cuadro de mensaje o alguna otra interfaz de usuario que indique que no tienen acceso y vuelva a la pestaña inicial.</span><span class="sxs-lookup"><span data-stu-id="34ba8-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="34ba8-112">Al implementar esta funcionalidad en las aplicaciones de producción, puede realizar esta comprobación de credenciales durante el evento <xref:System.Windows.Forms.Form.Load> del formulario.</span><span class="sxs-lookup"><span data-stu-id="34ba8-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="34ba8-113">Esto le permitirá ocultar la pestaña antes de que se muestre cualquier interfaz de usuario, que es un enfoque mucho más limpio para la programación.</span><span class="sxs-lookup"><span data-stu-id="34ba8-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="34ba8-114">La metodología que se usa a continuación (comprobar las credenciales y deshabilitar la pestaña durante el <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> evento) es con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="34ba8-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="34ba8-115">Opcionalmente, si tiene más de dos páginas de fichas, muestre una página de ficha diferente de la original.</span><span class="sxs-lookup"><span data-stu-id="34ba8-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="34ba8-116">En el ejemplo siguiente, se <xref:System.Windows.Forms.CheckBox> usa un control en lugar de comprobar las credenciales, ya que los criterios para el acceso a la pestaña variarán en función de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34ba8-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="34ba8-117">Cuando se <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> genera el evento, si la comprobación de credenciales es true (es decir, la casilla está activada) y la pestaña seleccionada `TabPage2` es (en `TabPage2` este ejemplo, la pestaña con la información confidencial), se muestra.</span><span class="sxs-lookup"><span data-stu-id="34ba8-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="34ba8-118">De lo `TabPage3` contrario, se muestra y se muestra un cuadro de mensaje al usuario, que indica que no tenía los privilegios de acceso adecuados.</span><span class="sxs-lookup"><span data-stu-id="34ba8-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="34ba8-119">En el código siguiente se presupone un formulario <xref:System.Windows.Forms.CheckBox> con un`CredentialCheck`control () <xref:System.Windows.Forms.TabControl> y un control con tres páginas de fichas.</span><span class="sxs-lookup"><span data-stu-id="34ba8-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="34ba8-120">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="34ba8-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="34ba8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="34ba8-121">See also</span></span>

- [<span data-ttu-id="34ba8-122">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="34ba8-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="34ba8-123">Cómo: Agregar un control a una página de fichas</span><span class="sxs-lookup"><span data-stu-id="34ba8-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="34ba8-124">Cómo: Agregar y quitar pestañas con el Windows Forms TabControl</span><span class="sxs-lookup"><span data-stu-id="34ba8-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="34ba8-125">Procedimientos: Cambiar la apariencia de la Windows Forms TabControl</span><span class="sxs-lookup"><span data-stu-id="34ba8-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
