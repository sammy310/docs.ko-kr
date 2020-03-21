---
title: IEnumerable 구현
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266913"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a><span data-ttu-id="cdcd2-102">연습: 시각적 기본에서 IEnumerable(T) 구현</span><span class="sxs-lookup"><span data-stu-id="cdcd2-102">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>
<span data-ttu-id="cdcd2-103">인터페이스는 <xref:System.Collections.Generic.IEnumerable%601> 한 번에 하나의 항목값 시퀀스를 반환할 수 있는 클래스에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-103">The <xref:System.Collections.Generic.IEnumerable%601> interface is implemented by classes that can return a sequence of values one item at a time.</span></span> <span data-ttu-id="cdcd2-104">한 번에 하나의 항목을 반환하는 이점은 전체 데이터 집합을 메모리에 로드할 필요가 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-104">The advantage of returning data one item at a time is that you do not have to load the complete set of data into memory to work with it.</span></span> <span data-ttu-id="cdcd2-105">데이터에서 단일 항목을 로드하려면 충분한 메모리만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-105">You only have to use sufficient memory to load a single item from the data.</span></span> <span data-ttu-id="cdcd2-106">인터페이스를 `IEnumerable(T)` 구현하는 클래스는 루프 `For Each` 또는 LINQ 쿼리와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-106">Classes that implement the `IEnumerable(T)` interface can be used with `For Each` loops or LINQ queries.</span></span>  
  
 <span data-ttu-id="cdcd2-107">예를 들어 큰 텍스트 파일을 읽고 특정 검색 조건과 일치하는 파일에서 각 줄을 반환해야 하는 응용 프로그램을 생각해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-107">For example, consider an application that must read a large text file and return each line from the file that matches particular search criteria.</span></span> <span data-ttu-id="cdcd2-108">응용 프로그램은 LINQ 쿼리를 사용하여 지정된 조건과 일치하는 파일에서 줄을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-108">The application uses a LINQ query to return lines from the file that match the specified criteria.</span></span> <span data-ttu-id="cdcd2-109">LINQ 쿼리를 사용하여 파일의 내용을 쿼리하기 위해 응용 프로그램은 파일의 내용을 배열 또는 컬렉션에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-109">To query the contents of the file by using a LINQ query, the application could load the contents of the file into an array or a collection.</span></span> <span data-ttu-id="cdcd2-110">그러나 전체 파일을 배열 또는 컬렉션에 로드하면 필요한 것보다 훨씬 많은 메모리가 소비됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-110">However, loading the whole file into an array or collection would consume far more memory than is required.</span></span> <span data-ttu-id="cdcd2-111">LINQ 쿼리대신 열거 가능한 클래스를 사용하여 파일 내용을 쿼리하고 검색 조건과 일치하는 값만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-111">The LINQ query could instead query the file contents by using an enumerable class, returning only values that match the search criteria.</span></span> <span data-ttu-id="cdcd2-112">일치하는 값만 몇 개만 반환하는 쿼리는 메모리를 훨씬 적게 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-112">Queries that return only a few matching values would consume far less memory.</span></span>  
  
 <span data-ttu-id="cdcd2-113">원본 데이터를 열거 가능한 <xref:System.Collections.Generic.IEnumerable%601> 데이터로 노출하도록 인터페이스를 구현하는 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-113">You can create a class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface to expose source data as enumerable data.</span></span> <span data-ttu-id="cdcd2-114">인터페이스를 `IEnumerable(T)` 구현하는 클래스에는 원본 데이터를 반복하기 <xref:System.Collections.Generic.IEnumerator%601> 위해 인터페이스를 구현하는 다른 클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-114">Your class that implements the `IEnumerable(T)` interface will require another class that implements the <xref:System.Collections.Generic.IEnumerator%601> interface to iterate through the source data.</span></span> <span data-ttu-id="cdcd2-115">이 두 클래스를 사용하면 데이터의 항목을 특정 유형으로 순차적으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-115">These two classes enable you to return items of data sequentially as a specific type.</span></span>  
  
 <span data-ttu-id="cdcd2-116">이 연습에서는 `IEnumerable(Of String)` 인터페이스를 구현하는 클래스와 한 번에 한 줄에 `IEnumerator(Of String)` 텍스트 파일을 읽는 인터페이스를 구현하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-116">In this walkthrough, you will create a class that implements the `IEnumerable(Of String)` interface and a class that implements the `IEnumerator(Of String)` interface to read a text file one line at a time.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a><span data-ttu-id="cdcd2-117">열거가능한 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="cdcd2-117">Creating the Enumerable Class</span></span>  
  
<span data-ttu-id="cdcd2-118">**열거 가능한 클래스 프로젝트 만들기**</span><span class="sxs-lookup"><span data-stu-id="cdcd2-118">**Create the enumerable class project**</span></span>

1. <span data-ttu-id="cdcd2-119">시각적 기본에서 **파일** 메뉴에서 **새로** 를 가리킨 다음 **프로젝트를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-119">In Visual Basic, on the **File** menu, point to **New** and then click **Project**.</span></span>

1. <span data-ttu-id="cdcd2-120">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-120">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="cdcd2-121">**템플릿** 창에서 **클래스 라이브러리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-121">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="cdcd2-122">**이름** 상자에 `StreamReaderEnumerable`을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-122">In the **Name** box, type `StreamReaderEnumerable`, and then click **OK**.</span></span> <span data-ttu-id="cdcd2-123">새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-123">The new project is displayed.</span></span>

1. <span data-ttu-id="cdcd2-124">**솔루션 탐색기에서**Class1.vb 파일을 마우스 오른쪽 단추로 클릭하고 **이름 바꾸기를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-124">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="cdcd2-125">파일 이름을 `StreamReaderEnumerable.vb`로 바꾸고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-125">Rename the file to `StreamReaderEnumerable.vb` and press ENTER.</span></span> <span data-ttu-id="cdcd2-126">파일 이름을 바꾸면 클래스 이름도 `StreamReaderEnumerable`으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-126">Renaming the file will also rename the class to `StreamReaderEnumerable`.</span></span> <span data-ttu-id="cdcd2-127">이 클래스는 `IEnumerable(Of String)` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-127">This class will implement the `IEnumerable(Of String)` interface.</span></span>

1. <span data-ttu-id="cdcd2-128">StreamReader열화 가능한 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가를**가리킨 다음 **새 항목을**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-128">Right-click the StreamReaderEnumerable project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="cdcd2-129">클래스 템플릿을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cdcd2-129">Select the **Class** template.</span></span> <span data-ttu-id="cdcd2-130">**이름** 상자에 `StreamReaderEnumerator.vb`를 입력하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-130">In the **Name** box, type `StreamReaderEnumerator.vb` and click **OK**.</span></span>

 <span data-ttu-id="cdcd2-131">이 프로젝트의 첫 번째 클래스는 열거 가능한 클래스이며 인터페이스를 `IEnumerable(Of String)` 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-131">The first class in this project is the enumerable class and will implement the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="cdcd2-132">이 일반 인터페이스는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하고 이 클래스의 소비자가 로 `String`입력된 값에 액세스할 수 있도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-132">This generic interface implements the <xref:System.Collections.IEnumerable> interface and guarantees that consumers of this class can access values typed as `String`.</span></span>  
  
<span data-ttu-id="cdcd2-133">**IEnumerable을 구현하는 코드 추가**</span><span class="sxs-lookup"><span data-stu-id="cdcd2-133">**Add the code to implement IEnumerable**</span></span>

1. <span data-ttu-id="cdcd2-134">StreamReaderEnumerable.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-134">Open the StreamReaderEnumerable.vb file.</span></span>

2. <span data-ttu-id="cdcd2-135">다음 `Public Class StreamReaderEnumerable`줄을 입력하고 ENTER를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-135">On the line after `Public Class StreamReaderEnumerable`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   <span data-ttu-id="cdcd2-136">Visual Basic은 인터페이스에 필요한 멤버로 클래스를 `IEnumerable(Of String)` 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-136">Visual Basic automatically populates the class with the members that are required by the `IEnumerable(Of String)` interface.</span></span>
  
3. <span data-ttu-id="cdcd2-137">이 열거형 클래스는 한 번에 한 줄의 텍스트 파일에서 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-137">This enumerable class will read lines from a text file one line at a time.</span></span> <span data-ttu-id="cdcd2-138">다음 코드를 클래스에 추가하여 파일 경로를 입력 매개 변수로 하는 공용 생성기를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-138">Add the following code to the class to expose a public constructor that takes a file path as an input parameter.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. <span data-ttu-id="cdcd2-139">인터페이스 메서드를 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 구현하면 클래스의 새 인스턴스가 `StreamReaderEnumerator` 반환됩니다. `IEnumerable(Of String)`</span><span class="sxs-lookup"><span data-stu-id="cdcd2-139">Your implementation of the <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method of the `IEnumerable(Of String)` interface will return a new instance of the `StreamReaderEnumerator` class.</span></span> <span data-ttu-id="cdcd2-140">인터페이스의 `GetEnumerator` 멤버만 노출해야 하기 `Private`때문에 인터페이스 메서드의 구현을 `IEnumerable(Of String)` 수행할 수 있습니다. `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="cdcd2-140">The implementation of the `GetEnumerator` method of the `IEnumerable` interface can be made `Private`, because you have to expose only members of the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="cdcd2-141">메서드에 대해 생성된 Visual `GetEnumerator` Basic 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-141">Replace the code that Visual Basic generated for the `GetEnumerator` methods with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
<span data-ttu-id="cdcd2-142">**IEnumerator를 구현하는 코드 추가**</span><span class="sxs-lookup"><span data-stu-id="cdcd2-142">**Add the code to implement IEnumerator**</span></span>

1. <span data-ttu-id="cdcd2-143">StreamReaderEnumerator.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-143">Open the StreamReaderEnumerator.vb file.</span></span>

2. <span data-ttu-id="cdcd2-144">다음 `Public Class StreamReaderEnumerator`줄을 입력하고 ENTER를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-144">On the line after `Public Class StreamReaderEnumerator`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   <span data-ttu-id="cdcd2-145">Visual Basic은 인터페이스에 필요한 멤버로 클래스를 `IEnumerator(Of String)` 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-145">Visual Basic automatically populates the class with the members that are required by the `IEnumerator(Of String)` interface.</span></span>

3. <span data-ttu-id="cdcd2-146">열거자 클래스는 텍스트 파일을 열고 파일 I/O를 수행하여 파일에서 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-146">The enumerator class opens the text file and performs the file I/O to read the lines from the file.</span></span> <span data-ttu-id="cdcd2-147">다음 코드를 클래스에 추가하여 파일 경로를 입력 매개 변수로 사용하는 공용 생성기를 노출하고 읽을 텍스트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-147">Add the following code to the class to expose a public constructor that takes a file path as an input parameter and open the text file for reading.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. <span data-ttu-id="cdcd2-148">및 `Current` `IEnumerator(Of String)` 인터페이스모두에 대한 속성은 텍스트 파일에서 현재 항목을 로 반환합니다. `String` `IEnumerator`</span><span class="sxs-lookup"><span data-stu-id="cdcd2-148">The `Current` properties for both the `IEnumerator(Of String)` and `IEnumerator` interfaces return the current item from the text file as a `String`.</span></span> <span data-ttu-id="cdcd2-149">인터페이스의 멤버만 `Current` 노출해야 하므로 `IEnumerator(Of String)` 인터페이스의 속성을 구현할 수 있습니다. `Private` `IEnumerator`</span><span class="sxs-lookup"><span data-stu-id="cdcd2-149">The implementation of the `Current` property of the `IEnumerator` interface can be made `Private`, because you have to expose only members of the `IEnumerator(Of String)` interface.</span></span> <span data-ttu-id="cdcd2-150">속성에 대해 생성된 Visual `Current` Basic 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-150">Replace the code that Visual Basic generated for the `Current` properties with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. <span data-ttu-id="cdcd2-151">인터페이스 `MoveNext` 메서드는 `IEnumerator` 텍스트 파일의 다음 항목으로 이동 하 고 `Current` 속성에서 반환 되는 값을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-151">The `MoveNext` method of the `IEnumerator` interface navigates to the next item in the text file and updates the value that is returned by the `Current` property.</span></span> <span data-ttu-id="cdcd2-152">읽을 항목이 더 이상 없는 `MoveNext` 경우 `False`메서드가 반환합니다. 그렇지 `MoveNext` 않으면 `True`메서드가 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-152">If there are no more items to read, the `MoveNext` method returns `False`; otherwise the `MoveNext` method returns `True`.</span></span> <span data-ttu-id="cdcd2-153">`MoveNext` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-153">Add the following code to the `MoveNext` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. <span data-ttu-id="cdcd2-154">`IEnumerator` 인터페이스의 메서드는 `Reset` 반복기를 텍스트 파일의 시작을 가리키도록 지시하고 현재 항목 값을 지웁히 지웁습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-154">The `Reset` method of the `IEnumerator` interface directs the iterator to point to the start of the text file and clears the current item value.</span></span> <span data-ttu-id="cdcd2-155">`Reset` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-155">Add the following code to the `Reset` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. <span data-ttu-id="cdcd2-156">인터페이스 `Dispose` 방법은 `IEnumerator` 관리되지 않는 모든 리소스가 처리기를 소멸하기 전에 해제되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-156">The `Dispose` method of the `IEnumerator` interface guarantees that all unmanaged resources are released before the iterator is destroyed.</span></span> <span data-ttu-id="cdcd2-157">개체에서 `StreamReader` 사용하는 파일 핸들은 관리되지 않는 리소스이며 거무자 인스턴스가 삭제되기 전에 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-157">The file handle that is used by the `StreamReader` object is an unmanaged resource and must be closed before the iterator instance is destroyed.</span></span> <span data-ttu-id="cdcd2-158">메서드에 대해 생성된 Visual `Dispose` Basic 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-158">Replace the code that Visual Basic generated for the `Dispose` method with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a><span data-ttu-id="cdcd2-159">샘플 이터레이터 사용</span><span class="sxs-lookup"><span data-stu-id="cdcd2-159">Using the Sample Iterator</span></span>

 <span data-ttu-id="cdcd2-160">루프 또는 LINQ 쿼리와 같이 구현하는 `IEnumerable`개체가 필요한 컨트롤 구조와 함께 코드에서 열거 가능한 클래스를 사용할 수 있습니다. `For Next`</span><span class="sxs-lookup"><span data-stu-id="cdcd2-160">You can use an enumerable class in your code together with control structures that require an object that implements `IEnumerable`, such as a `For Next` loop or a LINQ query.</span></span> <span data-ttu-id="cdcd2-161">다음 예제에서는 `StreamReaderEnumerable` LINQ 쿼리를 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="cdcd2-161">The following example shows the `StreamReaderEnumerable` in a LINQ query.</span></span>  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="cdcd2-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdcd2-162">See also</span></span>

- [<span data-ttu-id="cdcd2-163">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="cdcd2-163">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="cdcd2-164">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="cdcd2-164">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="cdcd2-165">루프 구조체</span><span class="sxs-lookup"><span data-stu-id="cdcd2-165">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="cdcd2-166">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="cdcd2-166">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
