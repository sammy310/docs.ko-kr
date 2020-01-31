---
title: FolderBrowserDialog 구성 요소를 사용 하 여 폴더 선택
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 313388442101f341cfed366143f3c9669fb45cbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742233"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="ee4e0-102">방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택</span><span class="sxs-lookup"><span data-stu-id="ee4e0-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="ee4e0-103">종종 Windows 애플리케이션을 만드는 경우 파일 집합을 저장하기 위해 사용자에게 폴더를 선택하도록 요구하는 메시지를 매우 빈번하게 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="ee4e0-104">Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용 하 여이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="ee4e0-105">Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더를 선택하려면</span><span class="sxs-lookup"><span data-stu-id="ee4e0-105">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="ee4e0-106">프로시저에서 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.Form.DialogResult%2A> 속성을 확인 하 여 대화 상자를 닫은 방법을 확인 하 고 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 속성 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="ee4e0-107">대화 상자의 트리 보기에 표시 되는 최상위 폴더를 설정 해야 하는 경우 <xref:System.Environment.SpecialFolder> 열거의 멤버를 사용 하는 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="ee4e0-108">또한 폴더-브라우저 트리 보기의 맨 위에 표시 되는 텍스트 문자열을 지정 하는 <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="ee4e0-109">아래 예제에서 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소는 Visual Studio에서 프로젝트를 만들고 저장할 폴더를 선택 하 라는 메시지가 표시 되는 폴더를 선택 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="ee4e0-110">이 예제에서는 폴더 이름이 폼의 <xref:System.Windows.Forms.TextBox> 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="ee4e0-111">사용자가 오류 또는 다른 문제가 있을 경우 선택 항목을 편집할 수 있도록 <xref:System.Windows.Forms.TextBox> 컨트롤과 같은 편집 가능한 영역에 위치를 배치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="ee4e0-112">이 예제에서는 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소와 <xref:System.Windows.Forms.TextBox> 컨트롤을 포함 하는 폼을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

    ```vb
    Public Sub ChooseFolder()
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then
            TextBox1.Text = FolderBrowserDialog1.SelectedPath
        End If
    End Sub
    ```

    ```csharp
    public void ChooseFolder()
    {
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)
        {
            textBox1.Text = folderBrowserDialog1.SelectedPath;
        }
    }
    ```

    ```cpp
    public:
       void ChooseFolder()
       {
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)
          {
             textBox1->Text = folderBrowserDialog1->SelectedPath;
          }
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="ee4e0-113">이 클래스를 사용 하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermissionAccess> 열거형의 일부인 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 속성에서 부여 된 권한 수준이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="ee4e0-114">부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="ee4e0-115">자세한 내용은 [코드 액세스 보안 기본 사항](../../misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="ee4e0-116">파일을 저장하는 방법에 대한 자세한 내용은 [방법: SaveFileDialog 구성 요소를 사용하여 파일 저장](how-to-save-files-using-the-savefiledialog-component.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee4e0-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ee4e0-117">참조</span><span class="sxs-lookup"><span data-stu-id="ee4e0-117">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="ee4e0-118">FolderBrowserDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ee4e0-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="ee4e0-119">FolderBrowserDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ee4e0-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
