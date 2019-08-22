---
title: '방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: be17d5e6a12824c1c9edc867c99e77a6a1437a36
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658592"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="39a1b-102">방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="39a1b-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="39a1b-103">여러 가지 방법으로 <xref:System.Windows.Forms.ImageList> 구성 요소에 이미지를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="39a1b-104">와 <xref:System.Windows.Forms.ImageList>연결 된 스마트 태그를 사용 하 여 이미지를 매우 빠르게 추가 하거나,의 다른 여러 속성 <xref:System.Windows.Forms.ImageList>을 설정 하는 경우 속성 창에 이미지를 추가 하는 것이 더 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="39a1b-105">코드를 사용 하 여 이미지를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-105">You can also add images by using code.</span></span> <span data-ttu-id="39a1b-106">코드를 사용 하 여 이미지를 추가 하는 방법에 [대 한 자세한 내용은 방법: Windows Forms ImageList 구성 요소](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 사용 하 여 이미지를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="39a1b-107">일반적으로 구성 요소 <xref:System.Windows.Forms.ImageList> 는 컨트롤과 연결 되기 전에 이미지를 사용 하 여 채워야 하지만 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>

### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="39a1b-108">속성 창를 사용 하 여 이미지를 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="39a1b-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="39a1b-109"><xref:System.Windows.Forms.ImageList> 구성 요소를 선택 하거나 폼에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="39a1b-110">속성 창에서![ 속성<xref:System.Windows.Forms.ImageList.Images%2A> 옆에 있는 줄임표 단추 (Visual](./media/visual-studio-ellipsis-button.png)Studio 속성 창의 줄임표 단추 (...))를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="39a1b-111">**이미지 컬렉션 편집기**에서 **추가** 또는 **제거** 를 클릭 하 여 목록에서 이미지를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="39a1b-112">스마트 태그를 사용 하 여 이미지를 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="39a1b-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="39a1b-113"><xref:System.Windows.Forms.ImageList> 구성 요소를 선택 하거나 폼에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="39a1b-114">스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="39a1b-115">**ImageList 작업** 대화 상자에서 **이미지 선택**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-115">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="39a1b-116">**이미지 컬렉션 편집기** 에서 **추가** 또는 **제거** 를 클릭 하 여 목록에서 이미지를 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="39a1b-116">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="39a1b-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="39a1b-117">See also</span></span>

- [<span data-ttu-id="39a1b-118">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="39a1b-118">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="39a1b-119">연습: Windows Forms 컨트롤에서 스마트 태그를 사용 하 여 일반 작업 수행</span><span class="sxs-lookup"><span data-stu-id="39a1b-119">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="39a1b-120">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="39a1b-120">ImageList Component</span></span>](imagelist-component-windows-forms.md)
