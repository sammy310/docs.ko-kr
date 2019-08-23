---
title: '방법: 입력 마스크 설정'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949144"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="0cd7f-102">방법: 입력 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="0cd7f-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="0cd7f-103">마스킹된 텍스트 상자 컨트롤은 사용자 입력을 허용 하거나 거부 하는 선언적 구문을 지 원하는 향상 된 텍스트 상자 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="0cd7f-104">Mask 속성을 설정 하 여 응용 프로그램에 사용자 지정 유효성 검사 논리를 작성 하지 않고 허용 가능한 사용자 입력을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="0cd7f-105">자세한 내용은 <xref:System.Windows.Forms.MaskedTextBox> 클래스의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="0cd7f-106">수동으로 Mask 속성 설정</span><span class="sxs-lookup"><span data-stu-id="0cd7f-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="0cd7f-107">Mask 속성이 지 원하는 문자에 대해 잘 알고 있는 경우 해당 문자를 수동으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="0cd7f-108">Mask 속성이 지 원하는 문자에 대 한 요약은 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성의 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="0cd7f-109">Mask 속성을 수동으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0cd7f-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="0cd7f-110">**디자인** 뷰에서 a <xref:System.Windows.Forms.MaskedTextBox>를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="0cd7f-111">**속성** 창에서 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="0cd7f-112">원하는 마스크를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-112">Type the mask that you want.</span></span> <span data-ttu-id="0cd7f-113">예를 들어 `###`과 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="0cd7f-114">입력 마스크 대화 상자 사용</span><span class="sxs-lookup"><span data-stu-id="0cd7f-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="0cd7f-115">입력 마스크 대화 상자는 미리 정의 된 입력 마스크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="0cd7f-116">미리 정의 된 마스크를 변경 하거나 사용자 고유의 마스크를 수동으로 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="0cd7f-117">입력 마스크 대화 상자를 열려면</span><span class="sxs-lookup"><span data-stu-id="0cd7f-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="0cd7f-118">**디자인** 뷰에서 a <xref:System.Windows.Forms.MaskedTextBox>를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1. <span data-ttu-id="0cd7f-119">스마트 태그를 클릭 하 여 **MaskedTextBox 작업** 패널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2. <span data-ttu-id="0cd7f-120">**마스크 설정**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="0cd7f-121">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="0cd7f-121">\- or -</span></span>  
  
    1. <span data-ttu-id="0cd7f-122">**속성** 창에서 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2. <span data-ttu-id="0cd7f-123">속성 값 열에서 줄임표 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="0cd7f-124">**입력 마스크** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-124">The **Input Mask** dialog box appears.</span></span>  
  
### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="0cd7f-125">입력 마스크 대화 상자를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="0cd7f-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="0cd7f-126">필드 목록에서 미리 정의 된 마스크 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="0cd7f-127">필드 **마스크** 상자에서 미리 정의 된 마스크를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="0cd7f-128">필드 **마스크** 상자에 새 마스크를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="0cd7f-129">즉, 미리 정의 된 마스크 중 하나를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0cd7f-130">미리 보기 상자에는 <xref:System.Windows.Forms.MaskedTextBox>사용자에 게 표시 되는 문자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="0cd7f-131">이러한 문자는 사용자가 데이터를 올바르게 입력 하는 데 도움이 되는 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="0cd7f-132">**ValidatingType 사용** 확인란을 선택 하거나 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="0cd7f-133">**ValidatingType 사용** 확인란은 사용자가 데이터 입력을 확인 하는 데 데이터 형식을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="0cd7f-134">자세한 내용은 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="0cd7f-135">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="0cd7f-136">마스크는 **속성** 창의 **mask** 속성에 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cd7f-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd7f-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="0cd7f-137">See also</span></span>

- [<span data-ttu-id="0cd7f-138">연습: MaskedTextBox 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="0cd7f-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
