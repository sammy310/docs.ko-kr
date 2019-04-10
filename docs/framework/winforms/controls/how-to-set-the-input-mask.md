---
title: '방법: 입력 마스크 설정'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06eaf68fef167d63e6f8404dd5049f5445881d24
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331470"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="d4615-102">방법: 입력 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="d4615-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="d4615-103">마스킹된 텍스트 상자 컨트롤에는 수락 하거나 거부 하는 사용자 입력에 대 한 선언적 구문을 지 원하는 향상 된 텍스트 상자 컨트롤이입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="d4615-104">마스크 속성을 설정 하면 응용 프로그램에 사용자 지정 유효성 검사 논리를 작성 하지 않고 허용 되는 사용자 입력을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="d4615-105">자세한 내용은의 설명 섹션을 참조 하십시오.는 <xref:System.Windows.Forms.MaskedTextBox> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="d4615-106">마스크 속성을 수동으로 설정</span><span class="sxs-lookup"><span data-stu-id="d4615-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="d4615-107">마스크 속성을 지 원하는 문자에 익숙한 경우 수동으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="d4615-108">마스크 속성을 지 원하는 문자 요약이의 설명 섹션을 참조 하세요.를 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="d4615-109">마스크 속성을 수동으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d4615-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="d4615-110">**디자인** 뷰에서 select를 <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="d4615-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="d4615-111">에 **속성** 창 찾기는 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="d4615-112">마스크를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-112">Type the mask that you want.</span></span> <span data-ttu-id="d4615-113">예를 들어 `###`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="d4615-114">입력된 마스크 대화 상자를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d4615-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="d4615-115">입력 마스크 대화 상자에서 일부 미리 정의 된 입력된 마스크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="d4615-116">미리 정의 된 마스크를 변경 하거나 사용자 고유의 마스크를 수동으로 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="d4615-117">입력 마스크 대화 상자를 열려면</span><span class="sxs-lookup"><span data-stu-id="d4615-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="d4615-118">**디자인** 뷰에서 select를 <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="d4615-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="d4615-119">열려는 스마트 태그를 클릭 합니다 **MaskedTextBox 작업** 패널입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="d4615-120">클릭 **마스크 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="d4615-121">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="d4615-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="d4615-122">에 **속성** 창에서를 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="d4615-123">속성 값 열에서 줄임표 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="d4615-124">합니다 **입력 마스크** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="d4615-125">입력 마스크 대화 상자를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="d4615-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="d4615-126">(선택 사항) 목록에서 미리 정의 된 면 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="d4615-127">(선택 사항) 미리 정의 된 마스크를 편집 합니다 **마스크** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="d4615-128">(선택 사항) 에 새 마스크를 입력 합니다 **마스크** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="d4615-129">즉, 미리 정의 된 마스크 중 하나를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4615-130">사용자에 게 표시 되는 문자를 표시 하는 미리 보기 상자는 <xref:System.Windows.Forms.MaskedTextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="d4615-131">이러한 문자는 사용자가 데이터를 올바르게 입력 수 있는 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="d4615-132">선택 하거나 선택을 취소 합니다 **사용 하 여 ValidatingType** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="d4615-133">합니다 **사용 하 여 ValidatingType** 확인란 사용자가 데이터 입력을 확인 하는 데이터 형식 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="d4615-134">자세한 내용은 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4615-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="d4615-135">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="d4615-136">마스크에 입력 합니다 **마스크** 속성에는 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="d4615-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4615-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4615-137">See also</span></span>

- [<span data-ttu-id="d4615-138">연습: MaskedTextBox 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="d4615-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
