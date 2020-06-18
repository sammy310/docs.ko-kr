---
title: '방법: SaveFileDialog 구성 요소를 사용하여 파일 저장'
description: SaveFileDialog 구성 요소를 사용 하 여 파일 시스템을 검색 하 고 저장할 파일을 선택 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: cd773c3d4aa2b907eb09dd87c3fdbe138bf533bb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904405"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="709b0-103">방법: SaveFileDialog 구성 요소를 사용하여 파일 저장</span><span class="sxs-lookup"><span data-stu-id="709b0-103">How to: Save Files Using the SaveFileDialog Component</span></span>

<span data-ttu-id="709b0-104"><xref:System.Windows.Forms.SaveFileDialog>사용자는 구성 요소를 사용 하 여 파일 시스템을 검색 하 고 저장할 파일을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-104">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="709b0-105">대화 상자에서 사용자가 선택한 파일의 경로와 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-105">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="709b0-106">그러나 실제로 디스크에 파일을 쓰는 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-106">However, you must write the code to actually write the files to disk.</span></span>

### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="709b0-107">SaveFileDialog 구성 요소를 사용하여 파일을 저장하려면</span><span class="sxs-lookup"><span data-stu-id="709b0-107">To save a file using the SaveFileDialog component</span></span>

- <span data-ttu-id="709b0-108">**파일 저장** 대화 상자를 표시하고 사용자가 선택한 파일을 저장하는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-108">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>

  <span data-ttu-id="709b0-109"><xref:System.Windows.Forms.SaveFileDialog>구성 요소의 메서드를 사용 <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 하 여 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-109">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="709b0-110">이 메서드는 <xref:System.IO.Stream> 작성할 수 있는 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-110">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>

  <span data-ttu-id="709b0-111">아래 예제에서는 속성을 사용 하 여 <xref:System.Windows.Forms.DialogResult> 파일의 이름을 가져오고, 메서드를 사용 하 여 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-111">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="709b0-112"><xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>메서드는 파일을 쓸 스트림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-112">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>

  <span data-ttu-id="709b0-113">아래 예제에는 <xref:System.Windows.Forms.Button> 할당 된 이미지가 있는 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-113">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="709b0-114">단추를 클릭 하면 <xref:System.Windows.Forms.SaveFileDialog> .gif, .jpeg 및 .bmp 형식의 파일을 허용 하는 필터를 사용 하 여 구성 요소가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-114">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="709b0-115">[파일 저장] 대화 상자에서 이 형식의 파일을 선택하면 단추의 이미지가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-115">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="709b0-116">속성을 가져오거나 설정 하려면 <xref:System.Windows.Forms.FileDialog.FileName%2A> 어셈블리에 클래스에서 부여한 권한 수준이 필요 합니다 <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="709b0-116">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="709b0-117">부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-117">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="709b0-118">자세한 내용은 [Code Access Security Basics](../../misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="709b0-118">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

  <span data-ttu-id="709b0-119">이 예제에서는 폼의 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.ButtonBase.Image%2A> 속성이 .gif, .jpeg 또는 .bmp 형식의 파일로 설정 된 컨트롤을 포함 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-119">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>

  > [!NOTE]
  > <span data-ttu-id="709b0-120"><xref:System.Windows.Forms.FileDialog> <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> 상속으로 인해 클래스의 일부인 클래스의 속성은 <xref:System.Windows.Forms.SaveFileDialog> 하나의 기반 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-120">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="709b0-121">데이터를 특정 형식으로 저장하는 코드를 작성하는 경우(예: 파일을 일반 텍스트와 이진 형식으로 저장하는 경우) 이러한 인덱스가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-121">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="709b0-122">아래 예제에서 이 속성에 대해 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-122">This property is featured in the example below.</span></span>

  ```vb
  Private Sub Button2_Click(ByVal sender As System.Object, _
  ByVal e As System.EventArgs) Handles Button2.Click
      ' Displays a SaveFileDialog so the user can save the Image
      ' assigned to Button2.
      Dim saveFileDialog1 As New SaveFileDialog()
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"
      saveFileDialog1.Title = "Save an Image File"
      saveFileDialog1.ShowDialog()

      ' If the file name is not an empty string open it for saving.
      If saveFileDialog1.FileName <> "" Then
        ' Saves the Image via a FileStream created by the OpenFile method.
        Dim fs As System.IO.FileStream = Ctype _
            (saveFileDialog1.OpenFile(), System.IO.FileStream)
        ' Saves the Image in the appropriate ImageFormat based upon the
        ' file type selected in the dialog box.
        ' NOTE that the FilterIndex property is one-based.
        Select Case saveFileDialog1.FilterIndex
            Case 1
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Jpeg)

            Case 2
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Bmp)

            Case 3
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Gif)
          End Select

          fs.Close()
      End If
  End Sub
  ```

  ```csharp
  private void button2_Click(object sender, System.EventArgs e)
  {
      // Displays a SaveFileDialog so the user can save the Image
      // assigned to Button2.
      SaveFileDialog saveFileDialog1 = new SaveFileDialog();
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
      saveFileDialog1.Title = "Save an Image File";
      saveFileDialog1.ShowDialog();

      // If the file name is not an empty string open it for saving.
      if(saveFileDialog1.FileName != "")
      {
        // Saves the Image via a FileStream created by the OpenFile method.
        System.IO.FileStream fs =
            (System.IO.FileStream)saveFileDialog1.OpenFile();
        // Saves the Image in the appropriate ImageFormat based upon the
        // File type selected in the dialog box.
        // NOTE that the FilterIndex property is one-based.
        switch(saveFileDialog1.FilterIndex)
        {
            case 1 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Jpeg);
            break;

            case 2 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Bmp);
            break;

            case 3 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Gif);
            break;
        }

      fs.Close();
      }
  }
  ```

  ```cpp
  private:
      System::Void button2_Click(System::Object ^ sender,
        System::EventArgs ^ e)
      {
        // Displays a SaveFileDialog so the user can save the Image
        // assigned to Button2.
        SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();
        saveFileDialog1->Filter =
            "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
        saveFileDialog1->Title = "Save an Image File";
        saveFileDialog1->ShowDialog();
        // If the file name is not an empty string, open it for saving.
        if(saveFileDialog1->FileName != "")
        {
            // Saves the Image through a FileStream created by
            // the OpenFile method.
            System::IO::FileStream ^ fs =
              safe_cast\<System::IO::FileStream*>(
              saveFileDialog1->OpenFile());
            // Saves the Image in the appropriate ImageFormat based on
            // the file type selected in the dialog box.
            // Note that the FilterIndex property is one based.
            switch(saveFileDialog1->FilterIndex)
            {
              case 1 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Jpeg);
                  break;
              case 2 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Bmp);
                  break;
              case 3 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Gif);
                  break;
            }
        fs->Close();
        }
      }
  ```

  <span data-ttu-id="709b0-123">(Visual c # 및 Visual C++) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-123">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  <span data-ttu-id="709b0-124">파일 스트림 작성에 대 한 자세한 내용은 및을 참조 하십시오 <xref:System.IO.FileStream.BeginWrite%2A> <xref:System.IO.FileStream.Write%2A> .</span><span class="sxs-lookup"><span data-stu-id="709b0-124">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>

  > [!NOTE]
  > <span data-ttu-id="709b0-125">컨트롤과 같은 특정 컨트롤에 <xref:System.Windows.Forms.RichTextBox> 는 파일을 저장할 수 있는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709b0-125">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span>

## <a name="see-also"></a><span data-ttu-id="709b0-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="709b0-126">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="709b0-127">SaveFileDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="709b0-127">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
