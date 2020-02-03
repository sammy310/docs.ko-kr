---
title: ImageList 구성 요소를 사용 하 여 이미지 추가 또는 제거
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: f531003377395bf219775e5ddb48ceb0822ff0ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741505"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="a4b4a-102">방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="a4b4a-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="a4b4a-103">Windows Forms <xref:System.Windows.Forms.ImageList> 구성 요소는 일반적으로 컨트롤과 연결 되기 전에 이미지로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="a4b4a-104">그러나 이미지 목록을 컨트롤과 연결한 후에 이미지를 추가 하 고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4b4a-105">이미지를 제거할 때 연결 된 컨트롤의 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 속성이 여전히 유효한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="a4b4a-106">프로그래밍 방식으로 이미지를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="a4b4a-106">To add images programmatically</span></span>  
  
- <span data-ttu-id="a4b4a-107">이미지 목록의 <xref:System.Windows.Forms.ImageList.Images%2A> 속성 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="a4b4a-108">다음 코드 예제에서 이미지의 위치에 대해 설정 된 경로는 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="a4b4a-109">이 위치는 Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더가 포함 될 수 있다고 가정할 수 있으므로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a4b4a-110">이 위치를 선택 하면 최소한의 시스템 액세스 수준이 있는 사용자도 응용 프로그램을 안전 하 게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="a4b4a-111">다음 코드 예제에서는 <xref:System.Windows.Forms.ImageList> 컨트롤이 이미 추가 된 폼이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the   
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =   
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample   
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as   
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =   
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="a4b4a-112">키 값이 포함 된 이미지를 추가 하려면입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-112">To add images with a key value.</span></span>  
  
- <span data-ttu-id="a4b4a-113">키 값을 사용 하는 이미지 목록의 <xref:System.Windows.Forms.ImageList.Images%2A> 속성 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="a4b4a-114">다음 코드 예제에서 이미지의 위치에 대해 설정 된 경로는 **내 문서** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="a4b4a-115">이 위치는 Windows 운영 체제를 실행 하는 대부분의 컴퓨터에이 폴더가 포함 될 수 있다고 가정할 수 있으므로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a4b4a-116">이 위치를 선택 하면 최소한의 시스템 액세스 수준이 있는 사용자도 응용 프로그램을 안전 하 게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="a4b4a-117">다음 코드 예제에서는 <xref:System.Windows.Forms.ImageList> 컨트롤이 이미 추가 된 폼이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the   
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =   
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="a4b4a-118">모든 이미지를 프로그래밍 방식으로 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="a4b4a-118">To remove all images programmatically</span></span>  
  
- <span data-ttu-id="a4b4a-119"><xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> 메서드를 사용 하 여 단일 이미지 제거</span><span class="sxs-lookup"><span data-stu-id="a4b4a-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="a4b4a-120">,-또는-</span><span class="sxs-lookup"><span data-stu-id="a4b4a-120">,-or-</span></span>  
  
     <span data-ttu-id="a4b4a-121"><xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> 메서드를 사용 하 여 이미지 목록의 모든 이미지를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="a4b4a-122">키로 이미지를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="a4b4a-122">To remove images by key</span></span>  
  
- <span data-ttu-id="a4b4a-123">키를 사용 하 여 단일 이미지를 제거 하려면 <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b4a-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4b4a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4b4a-124">See also</span></span>

- [<span data-ttu-id="a4b4a-125">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a4b4a-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="a4b4a-126">ImageList 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="a4b4a-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="a4b4a-127">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="a4b4a-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
