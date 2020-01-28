---
title: 컨트롤에 의해 표시 되는 이미지 설정
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 5df0068c8462bbaab0cb0135de1dd1b91ababe06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746877"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="4d0af-102">방법: Windows Forms 컨트롤에 의해 표시 되는 이미지 설정</span><span class="sxs-lookup"><span data-stu-id="4d0af-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="4d0af-103">여러 가지 Windows Forms 컨트롤에서 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="4d0af-104">이러한 이미지는 저장 명령을 나타내는 단추의 디스켓 아이콘 처럼 컨트롤의 용도를 명확히 나타내는 아이콘 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="4d0af-105">또는 원하는 모양과 동작을 컨트롤에 제공 하기 위해 아이콘을 배경 이미지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="programmatic"></a><span data-ttu-id="4d0af-106">기능의</span><span class="sxs-lookup"><span data-stu-id="4d0af-106">Programmatic</span></span>

<span data-ttu-id="4d0af-107">컨트롤의 `Image` 또는 `BackgroundImage` 속성을 <xref:System.Drawing.Image>형식의 개체로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="4d0af-108">일반적으로 <xref:System.Drawing.Image.FromFile%2A> 메서드를 사용 하 여 파일에서 이미지를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-108">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="4d0af-109">다음 코드 예제에서 이미지의 위치에 대해 설정 된 경로는 **내 그림** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="4d0af-110">Windows 운영 체제를 실행 하는 대부분의 컴퓨터는이 디렉터리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-110">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="4d0af-111">이를 통해 최소한의 시스템 액세스 수준을 가진 사용자도 응용 프로그램을 안전 하 게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="4d0af-112">다음 코드 예제에서는 <xref:System.Windows.Forms.PictureBox> 컨트롤이 추가 된 폼이 이미 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a><span data-ttu-id="4d0af-113">Designer</span><span class="sxs-lookup"><span data-stu-id="4d0af-113">Designer</span></span>

1. <span data-ttu-id="4d0af-114">Visual Studio의 **속성** 창에서 컨트롤의 **Image** 또는 **BackgroundImage** 속성을 선택한 다음 줄임표 (Visual studio](./media/visual-studio-ellipsis-button.png)의 줄임표 단추![)를 선택 하 여 **리소스 선택** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-114">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](./media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box.</span></span>

2. <span data-ttu-id="4d0af-115">표시 하려는 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0af-115">Select the image you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d0af-116">참조</span><span class="sxs-lookup"><span data-stu-id="4d0af-116">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
