---
title: '방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 346d7107c9c17c5df06fa0e47f7a35355344f590
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880731"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="c2ad8-102">방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="c2ad8-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="c2ad8-103">이미지를 추가할 수 있습니다는 <xref:System.Windows.Forms.ImageList> 여러 가지 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="c2ad8-104">연결 된 스마트 태그를 사용 하 여 매우 신속 하 게 이미지를 추가할 수 있습니다 합니다 <xref:System.Windows.Forms.ImageList>에 다른 여러 속성을 설정 하는 경우 또는 <xref:System.Windows.Forms.ImageList>,이 더 편리할 속성 창 사용 하 여 이미지를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="c2ad8-105">또한 코드를 사용 하 여 이미지를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-105">You can also add images by using code.</span></span> <span data-ttu-id="c2ad8-106">코드를 사용 하 여 이미지를 추가 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 제거 이미지는 Windows Forms ImageList 구성 요소 추가 또는](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="c2ad8-107">채울 일반적으로 <xref:System.Windows.Forms.ImageList> 컨트롤과 연결 되지만 이것이 필요 하기 전에 이미지를 사용 하 여 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2ad8-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c2ad8-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c2ad8-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="c2ad8-111">추가 하거나 속성 창을 사용 하 여 이미지를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="c2ad8-111">To add or remove images by using the Properties window</span></span>  
  
1. <span data-ttu-id="c2ad8-112">선택 된 <xref:System.Windows.Forms.ImageList> 구성 요소를 폼에 추가 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="c2ad8-113">속성 창에서 줄임표 단추를 클릭 합니다. (![의 줄임표 단추 (...)의 Visual Studio 속성 창의](./media/visual-studio-ellipsis-button.png)) 옆에 <xref:System.Windows.Forms.ImageList.Images%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-113">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3. <span data-ttu-id="c2ad8-114">에 **이미지 컬렉션 편집기**, 클릭 **추가** 또는 **제거** 를 추가 하 여 목록에서 이미지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="c2ad8-115">스마트 태그를 사용 하 여 이미지 추가 또는 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="c2ad8-115">To add or remove images using the smart tag</span></span>  
  
1. <span data-ttu-id="c2ad8-116">선택 된 <xref:System.Windows.Forms.ImageList> 구성 요소를 폼에 추가 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2. <span data-ttu-id="c2ad8-117">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="c2ad8-117">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3. <span data-ttu-id="c2ad8-118">에 **ImageList 태스크** 대화 상자에서 **이미지 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4. <span data-ttu-id="c2ad8-119">에 **이미지 컬렉션 편집기** 클릭 **추가** 또는 **제거** 를 추가 하 여 목록에서 이미지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2ad8-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2ad8-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="c2ad8-120">See also</span></span>

- [<span data-ttu-id="c2ad8-121">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="c2ad8-121">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="c2ad8-122">연습: Forms 컨트롤 Windows에서 태그를 스마트를 사용 하 여 일반적인 작업 수행</span><span class="sxs-lookup"><span data-stu-id="c2ad8-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="c2ad8-123">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c2ad8-123">ImageList Component</span></span>](imagelist-component-windows-forms.md)
