---
title: '방법: 바인딩된 컨트롤 만들기 및 표시된 데이터 서식 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 052e619acb23fb2e25f42daf7b4eaaacb0688f31
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039431"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="ce9b8-102">방법: 바인딩된 컨트롤 만들기 및 표시된 데이터 서식 지정</span><span class="sxs-lookup"><span data-stu-id="ce9b8-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="ce9b8-103">Windows Forms 데이터 바인딩을 사용 하면 **서식 지정 및 고급 바인딩** 대화 상자를 사용 하 여 데이터 바인딩된 컨트롤에 표시 되는 데이터의 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>


### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="ce9b8-104">컨트롤을 바인딩하고 표시된 데이터의 서식을 지정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="ce9b8-105">데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-105">Connect to a data source.</span></span>

     <span data-ttu-id="ce9b8-106">자세한 내용은 [데이터 원본에 연결](../data/adonet/connecting-to-a-data-source.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-106">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="ce9b8-107">폼에서 컨트롤을 선택하고 속성 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-107">In the form, select the control, and then open the Properties window.</span></span>

3. <span data-ttu-id="ce9b8-108">**(데이터 바인딩)** 속성을 확장 한 다음 **(고급)** 상자에서 줄임표 단추 (![Visual Studio의 속성 창에 있는 줄임표 단추 (...)를 클릭 하 여 서식 지정 및 고급을 표시 합니다.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)  **바인딩** 대화 상자-해당 컨트롤에 대 한 속성의 전체 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="ce9b8-109">바인딩할 속성을 선택 하 고 **바인딩** 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-109">Select the property you want to bind, and then click the **Binding** arrow.</span></span>

     <span data-ttu-id="ce9b8-110">사용 가능한 데이터 소스 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="ce9b8-111">원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="ce9b8-112">예를 들어 데이터 세트의 테이블에서 열 값에 바인딩할 경우 데이터 세트 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="ce9b8-113">바인딩할 요소 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-113">Click the name of an element to bind to.</span></span>

7. <span data-ttu-id="ce9b8-114">형식 **형식** 상자에서 컨트롤에 표시 되는 데이터에 적용할 형식을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-114">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="ce9b8-115">모든 경우에 데이터 소스에 <xref:System.DBNull>이 있으면 컨트롤에 표시된 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="ce9b8-116">그러지 않으면 선택한 형식 유형에 따라 옵션이 약간 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="ce9b8-117">다음 표에서는 형식 유형 및 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="ce9b8-118">형식 유형</span><span class="sxs-lookup"><span data-stu-id="ce9b8-118">Format type</span></span>|<span data-ttu-id="ce9b8-119">서식 지정 옵션</span><span class="sxs-lookup"><span data-stu-id="ce9b8-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="ce9b8-120">서식 없음</span><span class="sxs-lookup"><span data-stu-id="ce9b8-120">No Formatting</span></span>|<span data-ttu-id="ce9b8-121">옵션 없음.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-121">No options.</span></span>|
    |<span data-ttu-id="ce9b8-122">숫자</span><span class="sxs-lookup"><span data-stu-id="ce9b8-122">Numeric</span></span>|<span data-ttu-id="ce9b8-123">**소수 자릿수** up-down 컨트롤을 사용 하 여 소수 자릿수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="ce9b8-124">통화</span><span class="sxs-lookup"><span data-stu-id="ce9b8-124">Currency</span></span>|<span data-ttu-id="ce9b8-125">**소수 자릿수** up-down 컨트롤을 사용 하 여 소수 자릿수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="ce9b8-126">날짜 시간</span><span class="sxs-lookup"><span data-stu-id="ce9b8-126">Date Time</span></span>|<span data-ttu-id="ce9b8-127">**유형** 선택 상자에서 항목 중 하나를 선택 하 여 날짜 및 시간을 표시 하는 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="ce9b8-128">지수</span><span class="sxs-lookup"><span data-stu-id="ce9b8-128">Scientific</span></span>|<span data-ttu-id="ce9b8-129">**소수 자릿수** up-down 컨트롤을 사용 하 여 소수 자릿수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="ce9b8-130">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ce9b8-130">Custom</span></span>|<span data-ttu-id="ce9b8-131">사용자 지정 서식 문자열 사용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="ce9b8-132">자세한 내용은 [서식 지정 형식](../../standard/base-types/formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-132">For more information, see [Formatting Types](../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="ce9b8-133">**참고:**  사용자 지정 서식 문자열은 데이터 소스와 바인딩된 컨트롤 간에 성공적으로 왕복된다고 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="ce9b8-134">대신에 바인딩에 대한 <xref:System.Windows.Forms.Binding.Parse> 또는 <xref:System.Windows.Forms.Binding.Format> 이벤트를 처리하고 이벤트 처리 코드에 사용자 지정 서식 지정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="ce9b8-135">**확인** 을 클릭 하 여 **서식 지정 및 고급 바인딩** 대화 상자를 닫고 속성 창로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="ce9b8-135">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce9b8-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="ce9b8-136">See also</span></span>

- [<span data-ttu-id="ce9b8-137">방법: Windows Form에 단순 바인딩된 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="ce9b8-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="ce9b8-138">Windows Forms에서 사용자 입력 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ce9b8-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="ce9b8-139">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="ce9b8-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
