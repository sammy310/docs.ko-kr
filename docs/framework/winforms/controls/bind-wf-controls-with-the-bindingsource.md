---
title: 디자이너를 사용 하 여 BindingSource 구성 요소와 컨트롤 바인딩
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 35b3fb7b9884f07dd6e2aef311a01d3090c44227
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744384"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="6813c-102">방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩</span><span class="sxs-lookup"><span data-stu-id="6813c-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="6813c-103">폼에 컨트롤을 추가 하 고 응용 프로그램에 대 한 사용자 인터페이스를 확인 한 후에는 런타임에 사용자가 응용 프로그램과 관련 된 데이터를 변경 하 고 저장할 수 있도록 컨트롤을 데이터 소스에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>

 <span data-ttu-id="6813c-104"><xref:System.Windows.Forms.BindingSource> 컨트롤을 폼과 데이터 소스 컨트롤 간의 브리지로 연결 하 여 Windows Forms에서 컨트롤 또는 일련의 컨트롤을 바인딩하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>

 <span data-ttu-id="6813c-105">폼에 있는 하나 이상의 컨트롤을 데이터에 바인딩할 수 있습니다. 다음 절차에서는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터 소스에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>

 <span data-ttu-id="6813c-106">이 절차를 완료 하려면 데이터베이스에서 파생 된 데이터 원본에 바인딩하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="6813c-107">다른 데이터 저장소에서 데이터 원본을 만드는 방법에 대 한 자세한 내용은 [새 데이터 소스 추가](/visualstudio/data-tools/add-new-data-sources)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6813c-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>

## <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="6813c-108">디자인 타임에 컨트롤을 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="6813c-108">To bind a control at design time</span></span>

1. <span data-ttu-id="6813c-109"><xref:System.Windows.Forms.TextBox> 컨트롤을 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-109">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>

2. <span data-ttu-id="6813c-110">**속성** 창에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-110">In the **Properties** window:</span></span>

    1. <span data-ttu-id="6813c-111">**(데이터 바인딩)** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-111">Expand the **(DataBindings)** node.</span></span>

    2. <span data-ttu-id="6813c-112"><xref:System.Windows.Forms.TextBox.Text%2A> 속성 옆의 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-112">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

         <span data-ttu-id="6813c-113">**DataSource** UI 형식 편집기가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-113">The **DataSource** UI type editor opens.</span></span>

         <span data-ttu-id="6813c-114">프로젝트 또는 폼에 대해 데이터 소스를 이전에 구성한 경우 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-114">If a data source has previously been configured for the project or form, it will appear.</span></span>

3. <span data-ttu-id="6813c-115">**프로젝트 데이터 소스 추가**를 클릭하여 데이터에 연결한 다음 데이터 소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-115">Click **Add Project Data Source** to connect to data and create a data source.</span></span>

4. <span data-ttu-id="6813c-116">**데이터 소스 구성 마법사** 시작 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-116">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>

5. <span data-ttu-id="6813c-117">**데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-117">On the **Choose a Data Source Type** page, select **Database**.</span></span>

6. <span data-ttu-id="6813c-118">**데이터 연결 선택** 페이지의 사용 가능한 연결 목록에서 데이터 연결을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-118">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="6813c-119">원하는 데이터 연결을 사용할 수 없는 경우 새 **연결** 을 선택 하 여 새 데이터 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-119">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>

7. <span data-ttu-id="6813c-120">**예, 연결을 저장** 합니다 .를 선택 하 여 응용 프로그램 구성 파일에 연결 문자열을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-120">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>

8. <span data-ttu-id="6813c-121">애플리케이션에 바인딩할 데이터베이스 개체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-121">Select the database objects to bring into your application.</span></span> <span data-ttu-id="6813c-122">이 경우 <xref:System.Windows.Forms.TextBox> 표시할 테이블의 필드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-122">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>

9. <span data-ttu-id="6813c-123">원하는 경우 기본 데이터 세트 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-123">Replace the default dataset name if you want.</span></span>

10. <span data-ttu-id="6813c-124">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-124">Click **Finish**.</span></span>

11. <span data-ttu-id="6813c-125">**속성** 창에서 <xref:System.Windows.Forms.TextBox.Text%2A> 속성 옆의 화살표를 다시 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-125">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="6813c-126">**DataSource** UI 형식 편집기에서 <xref:System.Windows.Forms.TextBox> 바인딩할 필드의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-126">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>

     <span data-ttu-id="6813c-127">**DataSource** UI 유형 편집기가 닫히고 해당 데이터 연결과 관련 된 데이터 집합, <xref:System.Windows.Forms.BindingSource> 및 테이블 어댑터가 폼에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6813c-127">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="6813c-128">참조</span><span class="sxs-lookup"><span data-stu-id="6813c-128">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="6813c-129">새 데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="6813c-129">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="6813c-130">[데이터 소스 창](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="6813c-130">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
