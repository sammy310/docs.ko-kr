---
title: '방법: Windows Form에 단순 바인딩된 컨트롤 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: df87f00e6e03de67c3fb1adc28472c96f4a47ef4
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015628"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="37c31-102">방법: Windows Form에 단순 바인딩된 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="37c31-102">How to: Create a simple-bound control on a Windows Form</span></span>

<span data-ttu-id="37c31-103">*단순 바인딩을*사용 하면 데이터 집합 테이블의 열 값과 같은 단일 데이터 요소를 컨트롤에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="37c31-104">컨트롤의 모든 속성을 데이터 값에 단순 하 게 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-104">You can simple-bind any property of a control to a data value.</span></span>

## <a name="to-simple-bind-a-control"></a><span data-ttu-id="37c31-105">컨트롤을 간단 하 게 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="37c31-105">To simple-bind a control</span></span>

1. <span data-ttu-id="37c31-106">데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-106">Connect to a data source.</span></span> <span data-ttu-id="37c31-107">자세한 내용은 [데이터 원본에 연결](../data/adonet/connecting-to-a-data-source.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37c31-107">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>

2. <span data-ttu-id="37c31-108">Visual Studio의 폼에서 컨트롤을 선택 하 고 **속성** 창을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-108">In Visual Studio, select the control on the form and display the **Properties** window.</span></span>

3. <span data-ttu-id="37c31-109">**(데이터 바인딩)** 속성을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-109">Expand the **(DataBindings)** property.</span></span>

     <span data-ttu-id="37c31-110">가장 자주 바인딩되는 속성은 **(데이터 바인딩)** 속성 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-110">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="37c31-111">예를 들어 대부분의 컨트롤에서 **Text** 속성은 가장 자주 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-111">For example, in most controls, the **Text** property is most frequently bound.</span></span>

4. <span data-ttu-id="37c31-112">바인딩하려는 속성이 일반적으로 바인딩되는 속성 중 하나가 아닌 경우 (고급) 상자의 **줄임표** ![단추 (...)를 클릭 하 여 **(고급)** 상자의 줄임표 단추 (... 속성 창)를](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)클릭 하 여 다음을 표시 **합니다. 서식 지정 및 고급 바인딩** 대화 상자를 사용 하 여 해당 컨트롤의 전체 속성 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-112">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>

5. <span data-ttu-id="37c31-113">바인딩할 속성을 선택 하 고 **바인딩**아래의 드롭다운 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-113">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>

     <span data-ttu-id="37c31-114">사용 가능한 데이터 소스 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-114">A list of available data sources is displayed.</span></span>

6. <span data-ttu-id="37c31-115">원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-115">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="37c31-116">예를 들어 데이터 세트의 테이블에서 열 값에 바인딩할 경우 데이터 세트 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-116">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

7. <span data-ttu-id="37c31-117">바인딩할 요소 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-117">Click the name of an element to bind to.</span></span>

8. <span data-ttu-id="37c31-118">**서식 지정 및 고급 바인딩** 대화 상자에서 작업 하는 경우 **확인** 을 클릭 하 여 **속성** 창으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-118">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>

9. <span data-ttu-id="37c31-119">컨트롤의 추가 속성을 바인딩하려면 3 ~ 7 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-119">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37c31-120">단순 바인딩된 컨트롤은 단일 데이터 요소만 표시 하기 때문에 단순 바인딩된 컨트롤을 사용 하 여 Windows Form에 탐색 논리를 포함 하는 것이 매우 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="37c31-120">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="37c31-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="37c31-121">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="37c31-122">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="37c31-122">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="37c31-123">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37c31-123">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
