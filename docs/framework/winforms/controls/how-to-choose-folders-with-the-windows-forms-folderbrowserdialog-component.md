---
title: FolderBrowserDialog 구성 요소를 사용 하 여 폴더 선택
description: 만든 Windows 응용 프로그램에서 Windows Forms FolderBrowserDialog 구성 요소를 사용 하 여 사용자에 게 폴더를 선택 하 라는 메시지를 표시 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 11d01bbaec3b82bc221960ebab5e33ca1aa302db
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903677"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="cd1da-103">방법: Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더 선택</span><span class="sxs-lookup"><span data-stu-id="cd1da-103">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="cd1da-104">종종 Windows 애플리케이션을 만드는 경우 파일 집합을 저장하기 위해 사용자에게 폴더를 선택하도록 요구하는 메시지를 매우 빈번하게 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-104">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="cd1da-105">Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소를 사용 하면이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-105">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="cd1da-106">Windows Forms FolderBrowserDialog 구성 요소를 사용하여 폴더를 선택하려면</span><span class="sxs-lookup"><span data-stu-id="cd1da-106">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="cd1da-107">프로시저에서 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 속성을 확인 <xref:System.Windows.Forms.Form.DialogResult%2A> 하 여 대화 상자를 닫은 방법을 확인 하 고 <xref:System.Windows.Forms.FolderBrowserDialog> 구성 요소의 속성 값을 가져옵니다 <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> .</span><span class="sxs-lookup"><span data-stu-id="cd1da-107">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="cd1da-108">대화 상자의 트리 뷰 내에 표시 되는 최상위 폴더를 설정 해야 하는 경우 열거형의 멤버를 사용 하는 속성을 설정 합니다 <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> <xref:System.Environment.SpecialFolder> .</span><span class="sxs-lookup"><span data-stu-id="cd1da-108">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="cd1da-109">또한 <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> 폴더의 맨 위에 표시 되는 텍스트 문자열을 지정 하는 속성을 설정할 수 있습니다-브라우저 트리 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-109">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="cd1da-110">아래 예제에서는 <xref:System.Windows.Forms.FolderBrowserDialog> Visual Studio에서 프로젝트를 만들고 저장할 폴더를 선택 하 라는 메시지가 표시 되는 것과 비슷한 방식으로 구성 요소를 사용 하 여 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-110">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="cd1da-111">이 예제에서는 폴더 이름이 <xref:System.Windows.Forms.TextBox> 폼의 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-111">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="cd1da-112"><xref:System.Windows.Forms.TextBox>사용자가 오류 또는 다른 문제가 발생 하는 경우 선택 항목을 편집할 수 있도록 위치를 컨트롤과 같은 편집 가능한 영역에 배치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-112">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="cd1da-113">이 예제에서는 구성 요소와 컨트롤을 포함 하는 폼을 가정 <xref:System.Windows.Forms.FolderBrowserDialog> <xref:System.Windows.Forms.TextBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-113">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

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
    > <span data-ttu-id="cd1da-114">이 클래스를 사용 하려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> 열거형의 일부인 속성에 부여 된 권한 수준이 필요 합니다 <xref:System.Security.Permissions.FileIOPermissionAccess> .</span><span class="sxs-lookup"><span data-stu-id="cd1da-114">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="cd1da-115">부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd1da-115">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="cd1da-116">자세한 내용은 [Code Access Security Basics](../../misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd1da-116">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="cd1da-117">파일을 저장하는 방법에 대한 자세한 내용은 [방법: SaveFileDialog 구성 요소를 사용하여 파일 저장](how-to-save-files-using-the-savefiledialog-component.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd1da-117">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cd1da-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd1da-118">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="cd1da-119">FolderBrowserDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cd1da-119">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="cd1da-120">FolderBrowserDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cd1da-120">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
