---
description: '자세한 정보: 선언 된 요소에 대 한 참조 (Visual Basic)'
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 75cc05381f01af00ac75995739647810fb7ff1d7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471437"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="af9d5-103">선언된 요소 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af9d5-103">References to Declared Elements (Visual Basic)</span></span>

<span data-ttu-id="af9d5-104">코드가 선언 된 요소를 참조 하는 경우 Visual Basic 컴파일러는 참조의 이름을 해당 이름의 적절 한 선언과 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-104">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="af9d5-105">동일한 이름을 사용 하 여 두 개 이상의 요소를 선언 하는 경우 해당 이름을 *정규화* 하 여 참조할 요소를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-105">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="af9d5-106">컴파일러는 이름 참조를 가장 *좁은 범위의* 이름 선언과 일치 시 키 려 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-106">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="af9d5-107">즉, 참조를 만드는 코드에서 시작 하 고 포함 하는 요소의 연속 수준을 통해 외부에서 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-107">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="af9d5-108">다음 예에서는 이름이 같은 두 변수에 대 한 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-108">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="af9d5-109">이 예제에서는 각각의 명명 된 두 변수를 `totalCount` 모듈의 서로 다른 범위 수준에서 선언 합니다 `container` .</span><span class="sxs-lookup"><span data-stu-id="af9d5-109">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="af9d5-110">한정자를 사용 하지 않고 프로시저를 표시 하는 경우 `showCount` `totalCount` Visual Basic 컴파일러는 범위를 가장 좁은 범위, 즉 내의 지역 선언으로 선언에 대 한 참조를 확인 합니다 `showCount` .</span><span class="sxs-lookup"><span data-stu-id="af9d5-110">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="af9d5-111">포함 하는 모듈을 사용 하 여 정규화 하는 경우 `totalCount` `container` 컴파일러는 더 넓은 범위의 선언에 대 한 참조를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-111">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="af9d5-112">요소 이름 한정</span><span class="sxs-lookup"><span data-stu-id="af9d5-112">Qualifying an Element Name</span></span>  

 <span data-ttu-id="af9d5-113">이 검색 프로세스를 재정의 하 고 더 광범위 한 범위에서 선언 된 이름을 지정 하려면 광범위 한 범위의 포함 요소로 이름을 *한정* 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-113">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="af9d5-114">경우에 따라 포함 하는 요소를 한 정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-114">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="af9d5-115">이름을 정규화 하면 원본 문의 앞에 target 요소가 정의 된 위치를 식별 하는 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-115">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="af9d5-116">이 정보를 *한정 문자열* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-116">This information is called a *qualification string*.</span></span> <span data-ttu-id="af9d5-117">하나 이상의 네임 스페이스와 모듈, 클래스 또는 구조를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-117">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="af9d5-118">한정 문자열은 대상 요소를 포함 하는 모듈, 클래스 또는 구조체를 명확 하 게 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-118">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="af9d5-119">컨테이너는 일반적으로 네임 스페이스를 포함 하는 다른 요소에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-119">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="af9d5-120">한정 문자열에 포함 된 요소를 여러 개 포함 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-120">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="af9d5-121">이름을 한정 하 여 선언 된 요소에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="af9d5-121">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="af9d5-122">요소가 정의 된 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-122">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="af9d5-123">여기에는 네임 스페이스 또는 네임 스페이스의 계층 구조도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-123">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="af9d5-124">가장 낮은 수준의 네임 스페이스 내에서 요소는 모듈, 클래스 또는 구조체에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-124">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2. <span data-ttu-id="af9d5-125">대상 요소의 위치를 기준으로 한정 경로를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-125">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="af9d5-126">최상위 네임 스페이스로 시작 하 고, 최하위 수준 네임 스페이스로 이동 하 고, target 요소를 포함 하는 모듈, 클래스 또는 구조체를 사용 하 여 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-126">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="af9d5-127">경로의 각 요소는 뒤에 오는 요소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-127">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="af9d5-128">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="af9d5-128">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="af9d5-129">대상 요소에 대 한 한정 문자열을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-129">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="af9d5-130">`.`경로의 모든 요소 뒤에 마침표 ()를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-130">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="af9d5-131">응용 프로그램에는 한정 문자열의 모든 요소에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-131">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="af9d5-132">일반적인 방법으로 target 요소를 참조 하는 식 또는 대입문을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-132">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="af9d5-133">대상 요소 이름 앞에 한정 문자열을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-133">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="af9d5-134">이름은 `.` 요소를 포함 하는 모듈, 클래스 또는 구조체 뒤에 오는 마침표 () 바로 뒤에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-134">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="af9d5-135">컴파일러는 한정 문자열을 사용 하 여 대상 요소 참조와 일치할 수 있는 명확 하 고 명확한 선언을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-135">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="af9d5-136">응용 프로그램에 동일한 이름을 가진 둘 이상의 프로그래밍 요소에 대 한 액세스 권한이 있는 경우 이름 참조를 정규화 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-136">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="af9d5-137">예를 들어 <xref:System.Windows.Forms> 및 <xref:System.Web.UI.WebControls> 네임 스페이스는 모두 `Label` 클래스 (및)를 포함 <xref:System.Windows.Forms.Label?displayProperty=nameWithType> <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-137">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="af9d5-138">응용 프로그램에서 두 가지를 모두 사용 하거나 자체 `Label` 클래스를 정의 하는 경우 서로 다른 개체를 구분 해야 합니다 `Label` .</span><span class="sxs-lookup"><span data-stu-id="af9d5-138">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="af9d5-139">변수 선언에 네임 스페이스 또는 가져오기 별칭을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-139">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="af9d5-140">다음 예에서는 가져오기 별칭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-140">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="af9d5-141">다른 포함 하는 요소의 멤버</span><span class="sxs-lookup"><span data-stu-id="af9d5-141">Members of Other Containing Elements</span></span>  

 <span data-ttu-id="af9d5-142">다른 클래스 또는 구조체의 비공유 멤버를 사용 하는 경우 먼저 해당 멤버 이름을 클래스 또는 구조체의 인스턴스를 가리키는 변수나 식으로 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-142">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="af9d5-143">다음 예제에서 `demoClass` 는 이라는 클래스의 인스턴스입니다 `class1` .</span><span class="sxs-lookup"><span data-stu-id="af9d5-143">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="af9d5-144">클래스 이름 자체를 사용 하 여 [공유](../../../language-reference/modifiers/shared.md)되지 않은 멤버를 한정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-144">You cannot use the class name itself to qualify a member that is not [Shared](../../../language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="af9d5-145">먼저 개체 변수 (이 경우)에서 인스턴스를 만든 `demoClass` 다음 변수 이름으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-145">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="af9d5-146">클래스 또는 구조체에 멤버가 있는 경우 `Shared` 해당 멤버를 클래스나 구조체 이름 또는 인스턴스를 가리키는 변수나 식으로 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-146">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="af9d5-147">모듈에는 별도의 인스턴스가 없으며 모든 멤버는 `Shared` 기본적으로입니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-147">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="af9d5-148">따라서 모듈 이름을 사용 하 여 모듈 멤버를 한정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-148">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="af9d5-149">다음 예에서는 모듈 멤버 프로시저에 대 한 정규화 된 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-149">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="af9d5-150">이 예제에서는 `Sub` `perform` 프로젝트의 다른 모듈에 있는 라는 두 개의 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-150">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="af9d5-151">각 항목은 고유한 모듈 내에서 한정 없이 지정할 수 있지만 다른 위치에서 참조 하는 경우에는 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-151">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="af9d5-152">의 최종 참조는 `module3` 한정 되지 않으므로 `perform` 컴파일러는 해당 참조를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-152">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="af9d5-153">프로젝트에 대 한 참조</span><span class="sxs-lookup"><span data-stu-id="af9d5-153">References to Projects</span></span>  

 <span data-ttu-id="af9d5-154">다른 프로젝트에 정의 된 [공용](../../../language-reference/modifiers/public.md) 요소를 사용 하려면 먼저 해당 프로젝트의 어셈블리 또는 형식 라이브러리에 대 한 *참조* 를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-154">To use [Public](../../../language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="af9d5-155">참조를 설정 하려면 **프로젝트** 메뉴에서 **참조 추가** 를 클릭 하거나 [-reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) 명령줄 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-155">To set a reference, click **Add Reference** on the **Project** menu, or use the [-reference (Visual Basic)](../../../reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="af9d5-156">예를 들어 .NET Framework의 XML 개체 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-156">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="af9d5-157">네임 스페이스에 대 한 참조를 설정 하는 경우와 <xref:System.Xml> 같은 해당 클래스를 선언 하 고 사용할 수 있습니다 <xref:System.Xml.XmlDocument> .</span><span class="sxs-lookup"><span data-stu-id="af9d5-157">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="af9d5-158">다음 예에서는 <xref:System.Xml.XmlDocument>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-158">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="af9d5-159">포함 하는 요소 가져오기</span><span class="sxs-lookup"><span data-stu-id="af9d5-159">Importing Containing Elements</span></span>  

 <span data-ttu-id="af9d5-160">[Imports 문 (.Net 네임 스페이스 및 형식)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) 을 사용 하 여 사용 하려는 모듈이 나 클래스를 포함 하는 네임 스페이스를 *가져올* 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-160">You can use the [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="af9d5-161">이렇게 하면 이름을 정규화 하지 않고 가져온 네임 스페이스에 정의 된 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-161">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="af9d5-162">다음 예제에서는 이전 예제를 다시 작성 하 여 <xref:System.Xml> 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-162">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="af9d5-163">또한 `Imports` 문은 가져온 각 네임 스페이스에 대 한 *가져오기 별칭* 을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-163">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="af9d5-164">이렇게 하면 소스 코드를 더 짧고 읽기 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-164">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="af9d5-165">다음 예제에서는 이전 예제를 다시 작성 하 여 `xD` 네임 스페이스에 대 한 별칭으로 사용 합니다 <xref:System.Xml> .</span><span class="sxs-lookup"><span data-stu-id="af9d5-165">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="af9d5-166">`Imports`문은 다른 프로젝트의 요소를 응용 프로그램에서 사용할 수 있도록 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-166">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="af9d5-167">즉, 참조를 설정 하는 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-167">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="af9d5-168">네임 스페이스를 가져오면 해당 네임 스페이스에 정의 된 이름을 한정 하는 요구 사항이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-168">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="af9d5-169">`Imports`문을 사용 하 여 모듈, 클래스, 구조체 및 열거형을 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-169">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="af9d5-170">그런 다음 이러한 가져온 요소의 멤버를 한정자 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-170">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="af9d5-171">그러나 클래스 또는 구조체의 인스턴스로 계산 되는 변수나 식으로 클래스와 구조체의 비공유 멤버를 항상 한정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-171">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="af9d5-172">명명 지침</span><span class="sxs-lookup"><span data-stu-id="af9d5-172">Naming Guidelines</span></span>  

 <span data-ttu-id="af9d5-173">이름이 같은 프로그래밍 요소를 두 개 이상 정의 하면 컴파일러에서 해당 이름에 대 한 참조를 확인 하려고 할 때 *이름 모호성이* 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-173">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="af9d5-174">둘 이상의 정의가 범위에 있거나, 범위에 정의가 없는 경우 참조는 해결할 수 없는입니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-174">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="af9d5-175">예제를 보려면이 도움말 페이지의 "정규화 된 참조 예제"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="af9d5-175">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="af9d5-176">모든 요소에 고유한 이름을 지정 하 여 이름 모호성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-176">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="af9d5-177">그런 다음 네임 스페이스, 모듈 또는 클래스를 사용 하 여 해당 이름을 한정할 필요 없이 모든 요소에 대 한 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-177">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="af9d5-178">실수로 잘못 된 요소를 참조할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-178">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="af9d5-179">섀도잉</span><span class="sxs-lookup"><span data-stu-id="af9d5-179">Shadowing</span></span>  

 <span data-ttu-id="af9d5-180">두 프로그래밍 요소가 동일한 이름을 공유 하는 경우 그 중 하나는 다른 *요소를 숨기 거 나 숨길* 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-180">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="af9d5-181">숨겨진 요소는 참조에 사용할 수 없습니다. 대신, 코드가 숨겨진 요소 이름을 사용 하는 경우 Visual Basic 컴파일러는 숨기는 요소로이를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af9d5-181">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="af9d5-182">예제에 대 한 자세한 설명은 [Visual Basic에서 숨기기](shadowing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af9d5-182">For a more detailed explanation with examples, see [Shadowing in Visual Basic](shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af9d5-183">추가 정보</span><span class="sxs-lookup"><span data-stu-id="af9d5-183">See also</span></span>

- [<span data-ttu-id="af9d5-184">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="af9d5-184">Declared Element Names</span></span>](declared-element-names.md)
- [<span data-ttu-id="af9d5-185">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="af9d5-185">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="af9d5-186">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="af9d5-186">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="af9d5-187">변수</span><span class="sxs-lookup"><span data-stu-id="af9d5-187">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="af9d5-188">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="af9d5-188">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="af9d5-189">New 연산자</span><span class="sxs-lookup"><span data-stu-id="af9d5-189">New Operator</span></span>](../../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="af9d5-190">공용</span><span class="sxs-lookup"><span data-stu-id="af9d5-190">Public</span></span>](../../../language-reference/modifiers/public.md)
