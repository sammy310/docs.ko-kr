---
title: '방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: c5d88e4942d96ee12e8b9f40156090c874386668
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046260"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="04e2e-102">방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장</span><span class="sxs-lookup"><span data-stu-id="04e2e-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="04e2e-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤은 다음과 같은 여러 형식 중 하나로 표시 되는 정보를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>

- <span data-ttu-id="04e2e-104">일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="04e2e-104">Plain text</span></span>

- <span data-ttu-id="04e2e-105">유니코드 일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="04e2e-105">Unicode plain text</span></span>

- <span data-ttu-id="04e2e-106">RTF (서식 있는 텍스트)</span><span class="sxs-lookup"><span data-stu-id="04e2e-106">Rich-Text Format (RTF)</span></span>

- <span data-ttu-id="04e2e-107">OLE 개체 대신 공백을 사용 하는 RTF</span><span class="sxs-lookup"><span data-stu-id="04e2e-107">RTF with spaces in place of OLE objects</span></span>

- <span data-ttu-id="04e2e-108">OLE 개체의 텍스트 표현을 포함 하는 일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="04e2e-108">Plain text with a textual representation of OLE objects</span></span>

<span data-ttu-id="04e2e-109">파일을 저장 하려면 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="04e2e-110">**SaveFile** 메서드를 사용 하 여 데이터를 스트림에 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="04e2e-111">자세한 내용은 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04e2e-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="04e2e-112">컨트롤의 내용을 파일에 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="04e2e-112">To save the contents of the control to a file</span></span>

1. <span data-ttu-id="04e2e-113">저장할 파일의 경로를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-113">Determine the path of the file to be saved.</span></span>

    <span data-ttu-id="04e2e-114">실제 응용 프로그램에서이 작업을 수행 하려면 일반적으로 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="04e2e-115">개요는 [Savefiledialog 구성 요소 개요](savefiledialog-component-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04e2e-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="04e2e-116">저장할 파일 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 및 선택적으로 <xref:System.Windows.Forms.RichTextBox> 파일 형식을 지정 하 여 컨트롤의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="04e2e-117">파일 이름을 유일한 인수로 사용 하 여 메서드를 호출 하는 경우 파일은 RTF로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="04e2e-118">다른 파일 형식을 지정하려면 <xref:System.Windows.Forms.RichTextBoxStreamType> 열거형의 값을 두 번째 인수로 사용하여 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="04e2e-119">아래 예제에서 서식 있는 텍스트 파일의 위치에 대해 설정 된 경로는 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="04e2e-120">이 위치는 Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더가 포함 된다고 가정할 수 있으므로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="04e2e-121">이 위치를 선택 하면 최소한의 시스템 액세스 수준을 가진 사용자도 응용 프로그램을 안전 하 게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="04e2e-122">아래 예제에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 이미 추가 된 폼을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="04e2e-123">이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="04e2e-124">응용 프로그램에서 파일을 만들어야 하는 경우 해당 응용 프로그램에 폴더에 대 한 만들기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="04e2e-125">권한은 액세스 제어 목록을 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="04e2e-126">파일이 이미 있는 경우 응용 프로그램은 낮은 권한인 쓰기 액세스만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="04e2e-127">가능 하면 배포 중에 파일을 만드는 것이 더 안전 하며, 폴더에 대 한 액세스를 만드는 대신 단일 파일에 대 한 읽기 권한만 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="04e2e-128">또한 루트 폴더나 Program Files 폴더보다 사용자 폴더에 데이터를 쓰는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="04e2e-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

## <a name="see-also"></a><span data-ttu-id="04e2e-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="04e2e-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="04e2e-130">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="04e2e-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="04e2e-131">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="04e2e-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
