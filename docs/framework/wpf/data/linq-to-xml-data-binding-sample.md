---
title: LINQ to XML 데이터 바인딩 예제
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921223"
---
# <a name="linq-to-xml-data-binding-sample"></a><span data-ttu-id="181f5-102">LINQ to XML 데이터 바인딩 샘플</span><span class="sxs-lookup"><span data-stu-id="181f5-102">LINQ to XML data binding sample</span></span>

<span data-ttu-id="181f5-103">이 문서에서는 사용자 인터페이스 구성 요소를 포함 된 XML 데이터 소스에 바인딩하는 WPF (Windows Presentation Foundation) 앱 인 LinqToXmlDataBinding 샘플에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-103">This article describes the LinqToXmlDataBinding sample, a Windows Presentation Foundation (WPF) app that binds user interface components to an embedded XML data source.</span></span>

## <a name="overview"></a><span data-ttu-id="181f5-104">개요</span><span class="sxs-lookup"><span data-stu-id="181f5-104">Overview</span></span>

<span data-ttu-id="181f5-105">LinqToXmlDataBinding 샘플은 및 XAML 소스 파일을 포함 C# 하는 WPF (Windows Presentation Foundation) 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-105">The LinqToXmlDataBinding sample is a Windows Presentation Foundation (WPF) app that contains C# and XAML source files.</span></span> <span data-ttu-id="181f5-106">포함 된 XML 문서는 책 목록을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-106">An embedded XML document defines a list of books.</span></span> <span data-ttu-id="181f5-107">앱을 통해 사용자는 책 항목을 보고, 추가 하 고, 삭제 하 고, 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-107">The app enables the user to view, add, delete, and edit the book entries.</span></span>

<span data-ttu-id="181f5-108">기본 소스 파일은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-108">There are two primary source files:</span></span>

- <span data-ttu-id="181f5-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md)에는 기본 창의 UI(사용자 인터페이스)에 대한 XAML 선언 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-109">[L2DBForm.xaml](l2dbform-xaml-source-code.md) contains the XAML declaration code for the user interface (UI) of the main window.</span></span> <span data-ttu-id="181f5-110">또한 책 목록에 대 한 포함 된 XML 문서 및 데이터 공급자를 정의 하는 창 리소스 섹션도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-110">It also contains a window resource section that defines a data provider and an embedded XML document for the book listings.</span></span>

- <span data-ttu-id="181f5-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md)에는 UI와 연결된 초기화 및 이벤트 처리 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-111">[L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md) contains the initialization and event-handling methods associated with the UI.</span></span>

<span data-ttu-id="181f5-112">기본 창은 다음 네 가지 세로 UI 섹션으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-112">The main window is divided into the following four vertical UI sections:</span></span>

- <span data-ttu-id="181f5-113">**XML**에서는 포함된 책 목록의 원시 XML 원본이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-113">**XML** displays the raw XML source of the embedded book listing.</span></span>

- <span data-ttu-id="181f5-114">**Book List**에서는 책 항목이 표준 텍스트로 표시되고 사용자가 개별 항목을 선택하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-114">**Book List** displays the book entries as standard text and enables the user to select and delete individual entries.</span></span>

- <span data-ttu-id="181f5-115">**Edit Selected Book**에서는 사용자가 현재 선택된 책 항목과 연결된 값을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-115">**Edit Selected Book** enables the user to edit the values associated with the currently selected book entry.</span></span>

- <span data-ttu-id="181f5-116">**Add New Book**에서는 사용자가 입력한 값에 따라 새 책 항목을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-116">**Add New Book** enables the creation of a new book entry based on values entered by the user.</span></span>

## <a name="run-the-sample"></a><span data-ttu-id="181f5-117">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="181f5-117">Run the sample</span></span>

<span data-ttu-id="181f5-118">이 섹션에서는 Visual Studio에서 LinqToXmlDataBinding 프로젝트를 만들고 빌드하는 방법과 결과로 생성 되는 WPF (LinqToXmlDataBinding Windows Presentation Foundation) 앱을 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-118">This section shows how to create and build the LinqToXmlDataBinding project in Visual Studio, and how to run the resulting LinqToXmlDataBinding Windows Presentation Foundation (WPF) app.</span></span>

### <a name="create-the-project"></a><span data-ttu-id="181f5-119">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-119">Create the project</span></span>

1. <span data-ttu-id="181f5-120">Visual Studio를 열고 이름이 **LinqToXmlDataBinding**인 C# **WPF 앱**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-120">Open Visual Studio and create a C# **WPF App** named **LinqToXmlDataBinding**.</span></span>

   <span data-ttu-id="181f5-121">프로젝트는 .NET Framework 3.5 이상을 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-121">The project should target the .NET Framework 3.5 (or later).</span></span>

1. <span data-ttu-id="181f5-122">이미 존재하지 않는 경우 다음 .NET 어셈블리에 대한 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-122">If not already present, add project references for the following .NET assemblies:</span></span>

    - <span data-ttu-id="181f5-123">System.Data</span><span class="sxs-lookup"><span data-stu-id="181f5-123">System.Data</span></span>
    - <span data-ttu-id="181f5-124">System.Data.DataSetExtensions</span><span class="sxs-lookup"><span data-stu-id="181f5-124">System.Data.DataSetExtensions</span></span>
    - <span data-ttu-id="181f5-125">System.Xml</span><span class="sxs-lookup"><span data-stu-id="181f5-125">System.Xml</span></span>
    - <span data-ttu-id="181f5-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="181f5-126">System.Xml</span></span>

1. <span data-ttu-id="181f5-127">**Ctnrl**+**Shift**+**B**를 눌러 솔루션을 빌드한 다음, **F5**를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-127">Build the solution by pressing **Ctrl**+**Shift**+**B**, then run it by pressing **F5**.</span></span>

   <span data-ttu-id="181f5-128">프로젝트가 오류 없이 컴파일되고 일반 WPF 애플리케이션으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-128">The project should compile without errors and run as a generic WPF application.</span></span>

### <a name="add-code"></a><span data-ttu-id="181f5-129">코드 추가</span><span class="sxs-lookup"><span data-stu-id="181f5-129">Add code</span></span>

1. <span data-ttu-id="181f5-130">**솔루션 탐색기**에서 소스 파일 **Window1.xaml**의 이름을 **L2XDBForm.xaml**로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-130">In **Solution Explorer**, rename the source file **Window1.xaml** to **L2XDBForm.xaml**.</span></span>

   <span data-ttu-id="181f5-131">종속 원본 파일 Window1.xaml.cs는 자동으로 L2XDBForm.xaml.cs로 이름이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-131">The dependent source file Window1.xaml.cs is automatically renamed to L2XDBForm.xaml.cs.</span></span>

1. <span data-ttu-id="181f5-132">**L2xdbform.xaml** 파일에 있는 소스 코드를 [l2dbform.xaml 소스 코드로](l2dbform-xaml-source-code.md)바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-132">Replace the source code found in the file **L2XDBForm.xaml** with the [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="181f5-133">이 파일 작업을 하려면 XAML 소스 뷰를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="181f5-133">Use the XAML source view to work with this file.</span></span>

1. <span data-ttu-id="181f5-134">마찬가지로 **L2XDBForm.xaml.cs** 의 소스를 [L2DBForm.xaml.cs 원본 코드로](l2dbform-xaml-cs-source-code.md)바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-134">Similarly, replace the source in **L2XDBForm.xaml.cs** with the [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

1. <span data-ttu-id="181f5-135">파일 **app.xaml**에서 **l2xdbform.xaml**를 사용 하 여 모든 문자열 **Window1** 을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-135">In the file **App.xaml**, replace all occurrences of the string **Window1.xaml** with **L2XDBForm.xaml**.</span></span>

1. <span data-ttu-id="181f5-136">**Ctrl**+**Shift**+**B**를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-136">Build the solution by pressing **Ctrl**+**Shift**+**B**.</span></span>

### <a name="run-the-app"></a><span data-ttu-id="181f5-137">앱 실행</span><span class="sxs-lookup"><span data-stu-id="181f5-137">Run the app</span></span>

<span data-ttu-id="181f5-138">LinqToXmlDataBinding 앱을 사용 하면 포함 된 XML 요소로 저장 된 책 목록을 보고 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-138">The LinqToXmlDataBinding app enables the user to view and manipulate a list of books that's stored as an embedded XML element.</span></span> <span data-ttu-id="181f5-139">**F5** 키 (디버깅 시작) 또는 **Ctrl**+**F5** 키 (디버깅 하지 않고 시작)를 눌러 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-139">Run the app by pressing **F5** (Start Debugging) or **Ctrl**+**F5** (Start Without Debugging).</span></span>

<span data-ttu-id="181f5-140">**LINQ to XML을 사용한 WPF 데이터 바인딩**이라는 제목의 프로그램 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-140">A program window with the title **WPF Data Binding using LINQ to XML** appears.</span></span>

<span data-ttu-id="181f5-141">UI의 맨 위 섹션에는 책 목록을 나타내는 원시 **XML** 이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-141">The top section of the UI displays the raw **XML** that represents the book list.</span></span> <span data-ttu-id="181f5-142">이 섹션은 마우스나 키보드를 통해 조작할 수 없도록 하는 WPF <xref:System.Windows.Controls.TextBlock> 컨트롤을 사용하여 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-142">It is displayed using a WPF <xref:System.Windows.Controls.TextBlock> control, which does not enable interaction through the mouse or keyboard.</span></span>

<span data-ttu-id="181f5-143">**Book List**라는 두 번째 세로 섹션에는 일반 텍스트로 정렬된 책 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-143">The second vertical section, labeled **Book List**, displays the books as a plain text ordered list.</span></span> <span data-ttu-id="181f5-144">이 섹션에는 마우스나 키보드를 통해 선택할 수 있도록 하는 <xref:System.Windows.Controls.ListBox> 컨트롤이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-144">It uses a <xref:System.Windows.Controls.ListBox> control that enables selection though the mouse or keyboard.</span></span>

### <a name="add-and-delete-books"></a><span data-ttu-id="181f5-145">책 추가 및 삭제</span><span class="sxs-lookup"><span data-stu-id="181f5-145">Add and delete books</span></span>

<span data-ttu-id="181f5-146">새 책을 목록에 추가 하려면 마지막 섹션인 **새 책 추가**에서 **ID** 및 **값** <xref:System.Windows.Controls.TextBox> 컨트롤에 값을 입력 한 다음 **북 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-146">To add a new book to the list, enter values into the **ID** and **Value** <xref:System.Windows.Controls.TextBox> controls in the last section, **Add New Book**, and then select **Add Book**.</span></span> <span data-ttu-id="181f5-147">책이 서적 및 XML 목록의 목록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-147">The book is appended to the list in both the book and XML listings.</span></span> <span data-ttu-id="181f5-148">이 프로그램에서는 입력 값의 유효성을 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-148">This program does not validate input values.</span></span>

<span data-ttu-id="181f5-149">목록에서 기존 책을 삭제 하려면 **Book list** 섹션에서 선택한 다음 **선택한 책 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-149">To delete an existing book from the list, select it in the **Book List** section, and then select **Remove Selected Book**.</span></span> <span data-ttu-id="181f5-150">책 항목은 책 및 원시 XML 원본 목록에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-150">The book entry is removed from both the book and the raw XML source listings.</span></span>

### <a name="edit-a-book-entry"></a><span data-ttu-id="181f5-151">책 항목 편집</span><span class="sxs-lookup"><span data-stu-id="181f5-151">Edit a book entry</span></span>

1. <span data-ttu-id="181f5-152">두 번째 **Book List** 섹션에서 책 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-152">Select the book entry in the second **Book List** section.</span></span>

   <span data-ttu-id="181f5-153">현재 값은 **선택한 책 편집** 섹션에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-153">Its current values are displayed in the **Edit Selected Book** section.</span></span>

1. <span data-ttu-id="181f5-154">키보드를 사용하여 값을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-154">Edit the values using the keyboard.</span></span> <span data-ttu-id="181f5-155"><xref:System.Windows.Controls.TextBox> 제어가 포커스를 잃으면 즉시 변경 내용이 XML 원본 및 책 목록에 자동으로 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="181f5-155">As soon as either <xref:System.Windows.Controls.TextBox> control loses focus, changes are automatically propagated to the XML source and book listings.</span></span>
