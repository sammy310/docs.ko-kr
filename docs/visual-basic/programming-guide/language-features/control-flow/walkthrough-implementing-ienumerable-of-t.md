---
title: IEnumerable 구현
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: f40fcf7e0724addc478b261dcd36d09e1d8a751a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333696"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a><span data-ttu-id="2f9af-102">연습: Visual Basic에서 IEnumerable(Of T) 구현</span><span class="sxs-lookup"><span data-stu-id="2f9af-102">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>
<span data-ttu-id="2f9af-103"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스는 한 번에 한 항목의 값 시퀀스를 반환할 수 있는 클래스에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-103">The <xref:System.Collections.Generic.IEnumerable%601> interface is implemented by classes that can return a sequence of values one item at a time.</span></span> <span data-ttu-id="2f9af-104">한 번에 하나의 항목으로 데이터를 반환 하는 장점은 전체 데이터 집합을 메모리에 로드 하 여 사용할 필요가 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-104">The advantage of returning data one item at a time is that you do not have to load the complete set of data into memory to work with it.</span></span> <span data-ttu-id="2f9af-105">데이터에서 단일 항목을 로드 하는 데 충분 한 메모리를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-105">You only have to use sufficient memory to load a single item from the data.</span></span> <span data-ttu-id="2f9af-106">`IEnumerable(T)` 인터페이스를 구현 하는 클래스는 `For Each` 루프 또는 LINQ 쿼리와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-106">Classes that implement the `IEnumerable(T)` interface can be used with `For Each` loops or LINQ queries.</span></span>  
  
 <span data-ttu-id="2f9af-107">예를 들어, 많은 텍스트 파일을 읽고 특정 검색 조건과 일치 하는 파일에서 각 줄을 반환 해야 하는 응용 프로그램이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-107">For example, consider an application that must read a large text file and return each line from the file that matches particular search criteria.</span></span> <span data-ttu-id="2f9af-108">응용 프로그램은 LINQ 쿼리를 사용 하 여 지정 된 조건과 일치 하는 파일에서 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-108">The application uses a LINQ query to return lines from the file that match the specified criteria.</span></span> <span data-ttu-id="2f9af-109">LINQ 쿼리를 사용 하 여 파일의 콘텐츠를 쿼리하려면 응용 프로그램에서 파일의 내용을 배열 또는 컬렉션에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-109">To query the contents of the file by using a LINQ query, the application could load the contents of the file into an array or a collection.</span></span> <span data-ttu-id="2f9af-110">그러나 전체 파일을 배열 또는 컬렉션에 로드 하면 필요한 것 보다 훨씬 많은 메모리가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-110">However, loading the whole file into an array or collection would consume far more memory than is required.</span></span> <span data-ttu-id="2f9af-111">LINQ 쿼리에서는 검색 조건과 일치 하는 값만 반환 하 여 열거 가능한 클래스를 사용 하 여 파일 콘텐츠를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-111">The LINQ query could instead query the file contents by using an enumerable class, returning only values that match the search criteria.</span></span> <span data-ttu-id="2f9af-112">일치 하는 값을 몇 개만 반환 하는 쿼리는 메모리를 훨씬 적게 소비 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-112">Queries that return only a few matching values would consume far less memory.</span></span>  
  
 <span data-ttu-id="2f9af-113">소스 데이터를 enumerable 데이터로 노출 하기 위해 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현 하는 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-113">You can create a class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface to expose source data as enumerable data.</span></span> <span data-ttu-id="2f9af-114">`IEnumerable(T)` 인터페이스를 구현 하는 클래스에는 소스 데이터를 반복 하기 위해 <xref:System.Collections.Generic.IEnumerator%601> 인터페이스를 구현 하는 다른 클래스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-114">Your class that implements the `IEnumerable(T)` interface will require another class that implements the <xref:System.Collections.Generic.IEnumerator%601> interface to iterate through the source data.</span></span> <span data-ttu-id="2f9af-115">이러한 두 클래스를 사용 하 여 데이터 항목을 특정 형식으로 순차적으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-115">These two classes enable you to return items of data sequentially as a specific type.</span></span>  
  
 <span data-ttu-id="2f9af-116">이 연습에서는 `IEnumerable(Of String)` 인터페이스를 구현 하는 클래스와 텍스트 파일을 한 번에 한 줄씩 읽도록 `IEnumerator(Of String)` 인터페이스를 구현 하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-116">In this walkthrough, you will create a class that implements the `IEnumerable(Of String)` interface and a class that implements the `IEnumerator(Of String)` interface to read a text file one line at a time.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a><span data-ttu-id="2f9af-117">열거 가능한 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="2f9af-117">Creating the Enumerable Class</span></span>  
  
<span data-ttu-id="2f9af-118">**열거 가능한 클래스 프로젝트 만들기**</span><span class="sxs-lookup"><span data-stu-id="2f9af-118">**Create the enumerable class project**</span></span>

1. <span data-ttu-id="2f9af-119">Visual Basic의 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-119">In Visual Basic, on the **File** menu, point to **New** and then click **Project**.</span></span>

1. <span data-ttu-id="2f9af-120">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-120">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="2f9af-121">**템플릿** 창에서 **클래스 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-121">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="2f9af-122">**이름** 상자에 `StreamReaderEnumerable`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-122">In the **Name** box, type `StreamReaderEnumerable`, and then click **OK**.</span></span> <span data-ttu-id="2f9af-123">새 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-123">The new project is displayed.</span></span>

1. <span data-ttu-id="2f9af-124">**솔루션 탐색기**에서 Class1 파일을 마우스 오른쪽 단추로 클릭 하 고 **이름 바꾸기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-124">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="2f9af-125">파일 이름을 `StreamReaderEnumerable.vb`으로 바꾸고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-125">Rename the file to `StreamReaderEnumerable.vb` and press ENTER.</span></span> <span data-ttu-id="2f9af-126">파일 이름을 바꾸면 클래스 이름도 `StreamReaderEnumerable`으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-126">Renaming the file will also rename the class to `StreamReaderEnumerable`.</span></span> <span data-ttu-id="2f9af-127">이 클래스는 `IEnumerable(Of String)` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-127">This class will implement the `IEnumerable(Of String)` interface.</span></span>

1. <span data-ttu-id="2f9af-128">StreamReaderEnumerable 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가**를 가리킨 다음 **새 항목**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-128">Right-click the StreamReaderEnumerable project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="2f9af-129">**클래스** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-129">Select the **Class** template.</span></span> <span data-ttu-id="2f9af-130">**이름** 상자에 `StreamReaderEnumerator.vb`를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-130">In the **Name** box, type `StreamReaderEnumerator.vb` and click **OK**.</span></span>

 <span data-ttu-id="2f9af-131">이 프로젝트의 첫 번째 클래스는 열거 가능한 클래스 이며 `IEnumerable(Of String)` 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-131">The first class in this project is the enumerable class and will implement the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="2f9af-132">이 제네릭 인터페이스는 <xref:System.Collections.IEnumerable> 인터페이스를 구현 하 고이 클래스의 소비자가 `String`형식 값에 액세스할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-132">This generic interface implements the <xref:System.Collections.IEnumerable> interface and guarantees that consumers of this class can access values typed as `String`.</span></span>  
  
<span data-ttu-id="2f9af-133">**IEnumerable을 구현 하는 코드를 추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f9af-133">**Add the code to implement IEnumerable**</span></span>

1. <span data-ttu-id="2f9af-134">StreamReaderEnumerable .vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-134">Open the StreamReaderEnumerable.vb file.</span></span>

2. <span data-ttu-id="2f9af-135">`Public Class StreamReaderEnumerable`후 줄에서 다음을 입력 하 고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-135">On the line after `Public Class StreamReaderEnumerable`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   <span data-ttu-id="2f9af-136">Visual Basic는 `IEnumerable(Of String)` 인터페이스에 필요한 멤버로 클래스를 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-136">Visual Basic automatically populates the class with the members that are required by the `IEnumerable(Of String)` interface.</span></span>
  
3. <span data-ttu-id="2f9af-137">이 열거 가능 클래스는 텍스트 파일에서 한 번에 한 줄씩 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-137">This enumerable class will read lines from a text file one line at a time.</span></span> <span data-ttu-id="2f9af-138">클래스에 다음 코드를 추가 하 여 파일 경로를 입력 매개 변수로 사용 하는 public 생성자를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-138">Add the following code to the class to expose a public constructor that takes a file path as an input parameter.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. <span data-ttu-id="2f9af-139">`IEnumerable(Of String)` 인터페이스의 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 메서드를 구현 하면 `StreamReaderEnumerator` 클래스의 새 인스턴스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-139">Your implementation of the <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method of the `IEnumerable(Of String)` interface will return a new instance of the `StreamReaderEnumerator` class.</span></span> <span data-ttu-id="2f9af-140">`IEnumerable(Of String)` 인터페이스의 멤버만 노출 해야 하기 때문에 `Private``IEnumerable` 인터페이스의 `GetEnumerator` 메서드를 구현 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-140">The implementation of the `GetEnumerator` method of the `IEnumerable` interface can be made `Private`, because you have to expose only members of the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="2f9af-141">`GetEnumerator` 메서드에 대해 생성 Visual Basic 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-141">Replace the code that Visual Basic generated for the `GetEnumerator` methods with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
<span data-ttu-id="2f9af-142">**IEnumerator를 구현 하는 코드를 추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2f9af-142">**Add the code to implement IEnumerator**</span></span>

1. <span data-ttu-id="2f9af-143">StreamReaderEnumerator .vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-143">Open the StreamReaderEnumerator.vb file.</span></span>

2. <span data-ttu-id="2f9af-144">`Public Class StreamReaderEnumerator`후 줄에서 다음을 입력 하 고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-144">On the line after `Public Class StreamReaderEnumerator`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   <span data-ttu-id="2f9af-145">Visual Basic는 `IEnumerator(Of String)` 인터페이스에 필요한 멤버로 클래스를 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-145">Visual Basic automatically populates the class with the members that are required by the `IEnumerator(Of String)` interface.</span></span>

3. <span data-ttu-id="2f9af-146">열거자 클래스는 텍스트 파일을 열고 파일 i/o를 수행 하 여 파일에서 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-146">The enumerator class opens the text file and performs the file I/O to read the lines from the file.</span></span> <span data-ttu-id="2f9af-147">클래스에 다음 코드를 추가 하 여 파일 경로를 입력 매개 변수로 사용 하는 public 생성자를 노출 하 고 읽을 수 있도록 텍스트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-147">Add the following code to the class to expose a public constructor that takes a file path as an input parameter and open the text file for reading.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. <span data-ttu-id="2f9af-148">`IEnumerator(Of String)` 및 `IEnumerator` 인터페이스의 `Current` 속성은 텍스트 파일에서 현재 항목을 `String`로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-148">The `Current` properties for both the `IEnumerator(Of String)` and `IEnumerator` interfaces return the current item from the text file as a `String`.</span></span> <span data-ttu-id="2f9af-149">`IEnumerator(Of String)` 인터페이스의 멤버만 노출 해야 하기 때문에 `Private``IEnumerator` 인터페이스의 `Current` 속성을 구현 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-149">The implementation of the `Current` property of the `IEnumerator` interface can be made `Private`, because you have to expose only members of the `IEnumerator(Of String)` interface.</span></span> <span data-ttu-id="2f9af-150">`Current` 속성에 대해 생성 Visual Basic 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-150">Replace the code that Visual Basic generated for the `Current` properties with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. <span data-ttu-id="2f9af-151">`IEnumerator` 인터페이스의 `MoveNext` 메서드는 텍스트 파일에서 다음 항목으로 이동 하 여 `Current` 속성에 의해 반환 되는 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-151">The `MoveNext` method of the `IEnumerator` interface navigates to the next item in the text file and updates the value that is returned by the `Current` property.</span></span> <span data-ttu-id="2f9af-152">읽을 항목이 더 이상 없으면 `MoveNext` 메서드에서 `False`을 반환 합니다. 그렇지 않으면 `MoveNext` 메서드는 `True`반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-152">If there are no more items to read, the `MoveNext` method returns `False`; otherwise the `MoveNext` method returns `True`.</span></span> <span data-ttu-id="2f9af-153">`MoveNext` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-153">Add the following code to the `MoveNext` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. <span data-ttu-id="2f9af-154">`IEnumerator` 인터페이스의 `Reset` 메서드는 반복기가 텍스트 파일의 시작을 가리키고 현재 항목 값을 지우는 것을 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-154">The `Reset` method of the `IEnumerator` interface directs the iterator to point to the start of the text file and clears the current item value.</span></span> <span data-ttu-id="2f9af-155">`Reset` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-155">Add the following code to the `Reset` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. <span data-ttu-id="2f9af-156">`IEnumerator` 인터페이스의 `Dispose` 메서드는 반복기가 제거 되기 전에 관리 되지 않는 모든 리소스가 해제 되도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-156">The `Dispose` method of the `IEnumerator` interface guarantees that all unmanaged resources are released before the iterator is destroyed.</span></span> <span data-ttu-id="2f9af-157">`StreamReader` 개체에서 사용 하는 파일 핸들은 관리 되지 않는 리소스 이며 반복기 인스턴스가 제거 되기 전에 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-157">The file handle that is used by the `StreamReader` object is an unmanaged resource and must be closed before the iterator instance is destroyed.</span></span> <span data-ttu-id="2f9af-158">`Dispose` 메서드에 대해 생성 Visual Basic 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-158">Replace the code that Visual Basic generated for the `Dispose` method with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)] 
  
## <a name="using-the-sample-iterator"></a><span data-ttu-id="2f9af-159">샘플 반복기 사용</span><span class="sxs-lookup"><span data-stu-id="2f9af-159">Using the Sample Iterator</span></span>

 <span data-ttu-id="2f9af-160">`For Next` 루프 또는 LINQ 쿼리와 같이 `IEnumerable`를 구현 하는 개체가 필요한 컨트롤 구조와 함께 코드에서 열거 가능한 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-160">You can use an enumerable class in your code together with control structures that require an object that implements `IEnumerable`, such as a `For Next` loop or a LINQ query.</span></span> <span data-ttu-id="2f9af-161">다음 예제에서는 LINQ 쿼리에서 `StreamReaderEnumerable`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f9af-161">The following example shows the `StreamReaderEnumerable` in a LINQ query.</span></span>  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2f9af-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f9af-162">See also</span></span>

- [<span data-ttu-id="2f9af-163">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="2f9af-163">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2f9af-164">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="2f9af-164">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="2f9af-165">루프 구조</span><span class="sxs-lookup"><span data-stu-id="2f9af-165">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="2f9af-166">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="2f9af-166">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
