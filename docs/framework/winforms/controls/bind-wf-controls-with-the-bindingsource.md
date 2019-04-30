---
title: '방법: 디자이너를 사용하여 Windows Forms 컨트롤에서 BindingSource 구성 요소 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: a4f87303954494e8e32d32e68fb3f1244f25680a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011722"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="d3f34-102">방법: 디자이너를 사용하여 Windows Forms 컨트롤에서 BindingSource 구성 요소 바인딩</span><span class="sxs-lookup"><span data-stu-id="d3f34-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="d3f34-103">폼에 컨트롤을 추가 하 고 응용 프로그램에 대 한 사용자 인터페이스를 확인한 후 런타임 시 사용자가 변경 하 고 수 응용 프로그램과 관련 된 데이터를 저장 되도록 데이터 원본에 컨트롤을 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>  
  
 <span data-ttu-id="d3f34-104">사용 하 여 가장 쉽게 수행 됩니다 Windows Forms 컨트롤 또는 일련의 컨트롤 바인딩는 <xref:System.Windows.Forms.BindingSource> 폼에 컨트롤 및 데이터 원본 사이의 연결 고리로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>  
  
 <span data-ttu-id="d3f34-105">하나 이상의 컨트롤을 폼에 데이터에 바인딩될 수 있습니다. 다음 절차에는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터 소스에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>  
  
 <span data-ttu-id="d3f34-106">절차를 완료 하려면 데이터베이스에서 파생 된 데이터 원본에 바인딩 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="d3f34-107">다른 데이터 저장소에서 데이터 원본 만들기에 대 한 자세한 내용은 참조 하세요. [새 데이터 원본을 추가](/visualstudio/data-tools/add-new-data-sources)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3f34-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d3f34-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d3f34-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3f34-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="d3f34-111">디자인 타임에 컨트롤을 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="d3f34-111">To bind a control at design time</span></span>  
  
1. <span data-ttu-id="d3f34-112">끌어서를 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-112">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>  
  
2. <span data-ttu-id="d3f34-113">에 **속성** 창:</span><span class="sxs-lookup"><span data-stu-id="d3f34-113">In the **Properties** window:</span></span>  
  
    1. <span data-ttu-id="d3f34-114">확장 된 **(DataBindings)** 노드.</span><span class="sxs-lookup"><span data-stu-id="d3f34-114">Expand the **(DataBindings)** node.</span></span>  
  
    2. <span data-ttu-id="d3f34-115">다음 화살표를 클릭 합니다 <xref:System.Windows.Forms.TextBox.Text%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-115">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
         <span data-ttu-id="d3f34-116">합니다 **DataSource** UI 형식 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-116">The **DataSource** UI type editor opens.</span></span>  
  
         <span data-ttu-id="d3f34-117">프로젝트 또는 폼에 대 한 데이터 소스를 이전에 구성 하는 경우 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-117">If a data source has previously been configured for the project or form, it will appear.</span></span>  
  
3. <span data-ttu-id="d3f34-118">**프로젝트 데이터 소스 추가**를 클릭하여 데이터에 연결한 다음 데이터 소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-118">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
4. <span data-ttu-id="d3f34-119">**데이터 소스 구성 마법사** 시작 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-119">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
5. <span data-ttu-id="d3f34-120">에 **데이터 소스 형식 선택** 페이지에서 **데이터베이스**합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-120">On the **Choose a Data Source Type** page, select **Database**.</span></span>  
  
6. <span data-ttu-id="d3f34-121">에 **데이터 연결 선택** 페이지의 사용 가능한 연결 목록에서 데이터 연결을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-121">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="d3f34-122">원하는 데이터 연결 선택 사용할 수 없으면 **새 연결** 는 새 데이터 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-122">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>  
  
7. <span data-ttu-id="d3f34-123">선택 **예, 연결을 저장 합니다** 응용 프로그램 구성 파일에서 연결 문자열을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-123">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
8. <span data-ttu-id="d3f34-124">애플리케이션에 바인딩할 데이터베이스 개체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-124">Select the database objects to bring into your application.</span></span> <span data-ttu-id="d3f34-125">이 예제의 경우 하려는 테이블의 필드를 선택 합니다 <xref:System.Windows.Forms.TextBox> 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-125">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>  
  
9. <span data-ttu-id="d3f34-126">원하는 경우 기본 데이터 세트 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-126">Replace the default dataset name if you want.</span></span>  
  
10. <span data-ttu-id="d3f34-127">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-127">Click **Finish**.</span></span>  
  
11. <span data-ttu-id="d3f34-128">에 **속성** 창 옆에 화살표를 클릭 합니다 <xref:System.Windows.Forms.TextBox.Text%2A> 속성 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-128">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="d3f34-129">에 **데이터 원본** UI 형식 편집기 바인딩할 필드의 이름을 선택 합니다 <xref:System.Windows.Forms.TextBox> 를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-129">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>  
  
     <span data-ttu-id="d3f34-130">합니다 **데이터 원본** UI 형식 편집기를 닫고 데이터 집합을 <xref:System.Windows.Forms.BindingSource> 및 관련 데이터 연결 폼에 추가 된 테이블 어댑터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-130">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f34-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3f34-131">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="d3f34-132">새 데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="d3f34-132">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="d3f34-133">[데이터 소스 창](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d3f34-133">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
