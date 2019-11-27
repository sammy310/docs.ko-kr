---
title: My.Forms 개체
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: db86704fdc8120ccac5f4489c80a515834ad888f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350369"
---
# <a name="myforms-object"></a><span data-ttu-id="c58ef-102">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="c58ef-102">My.Forms Object</span></span>

<span data-ttu-id="c58ef-103">현재 프로젝트에 선언 된 각 Windows form의 인스턴스에 액세스 하기 위한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>

## <a name="remarks"></a><span data-ttu-id="c58ef-104">주의</span><span class="sxs-lookup"><span data-stu-id="c58ef-104">Remarks</span></span>

<span data-ttu-id="c58ef-105">`My.Forms` 개체는 현재 프로젝트에 있는 각 폼의 인스턴스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="c58ef-106">속성의 이름은 속성이 액세스 하는 폼의 이름과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-106">The name of the property is the same as the name of the form that the property accesses.</span></span>

<span data-ttu-id="c58ef-107">한정자를 사용 하지 않고 폼 이름을 사용 하 여 `My.Forms` 개체에서 제공 하는 폼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="c58ef-108">속성 이름이 폼의 형식 이름과 동일 하기 때문에 기본 인스턴스가 있는 것 처럼 폼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="c58ef-109">예를 들어 `My.Forms.Form1.Show`은 `Form1.Show`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>

<span data-ttu-id="c58ef-110">`My.Forms` 개체는 현재 프로젝트와 연결 된 폼만 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="c58ef-111">참조 된 Dll에 선언 된 폼에 대 한 액세스 권한은 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="c58ef-112">DLL이 제공 하는 폼에 액세스 하려면 *DllName*로 작성 된 양식의 정규화 된 이름을 사용 해야 합니다. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="c58ef-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>

<span data-ttu-id="c58ef-113"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> 속성을 사용 하 여 모든 응용 프로그램의 열려 있는 폼의 컬렉션을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>

<span data-ttu-id="c58ef-114">개체 및 해당 속성은 Windows 응용 프로그램에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-114">The object and its properties are available only for Windows applications.</span></span>

## <a name="properties"></a><span data-ttu-id="c58ef-115">속성</span><span class="sxs-lookup"><span data-stu-id="c58ef-115">Properties</span></span>

<span data-ttu-id="c58ef-116">`My.Forms` 개체의 각 속성은 현재 프로젝트에 있는 폼의 인스턴스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="c58ef-117">속성의 이름은 속성이 액세스 하는 폼의 이름과 동일 하며, 속성 형식은 폼의 형식과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>

> [!NOTE]
> <span data-ttu-id="c58ef-118">이름 충돌이 발생 하는 경우 양식 액세스를 위한 속성 이름은 *RootNamespace*_*Namespace*\_*FormName*입니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="c58ef-119">예를 들어, 이러한 폼 중 하나가 루트 네임 스페이스 `WindowsApplication1`에 있고 네임 스페이스 `Namespace1`에 있는 경우 `Form1.`라는 두 개의 폼을 고려 합니다. `My.Forms.WindowsApplication1_Namespace1_Form1`를 통해 해당 폼에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>

<span data-ttu-id="c58ef-120">`My.Forms` 개체는 시작 시 만들어진 응용 프로그램 기본 폼의 인스턴스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="c58ef-121">다른 모든 폼의 경우 `My.Forms` 개체는 폼에 액세스 하 고 저장할 때 폼의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="c58ef-122">이후에 해당 속성에 액세스 하려고 하면 해당 폼의 인스턴스가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-122">Subsequent attempts to access that property return that instance of the form.</span></span>

<span data-ttu-id="c58ef-123">해당 폼의 속성에 `Nothing`을 할당 하 여 폼을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="c58ef-124">속성 setter는 폼의 <xref:System.Windows.Forms.Form.Close%2A> 메서드를 호출한 다음 `Nothing`를 저장 된 값에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="c58ef-125">`Nothing` 이외의 값을 속성에 할당 하면 setter가 <xref:System.ArgumentException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="c58ef-126">`Is` 또는 `IsNot` 연산자를 사용 하 여 `My.Forms` 개체의 속성이 폼의 인스턴스를 저장 하는지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="c58ef-127">이러한 연산자를 사용 하 여 속성 값이 `Nothing`있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>

> [!NOTE]
> <span data-ttu-id="c58ef-128">일반적으로 `Is` 또는 `IsNot` 연산자는 비교를 수행 하기 위해 속성의 값을 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="c58ef-129">그러나 속성이 현재 `Nothing`를 저장 하는 경우 속성은 폼의 새 인스턴스를 만든 다음 해당 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="c58ef-130">그러나 Visual Basic 컴파일러는 `My.Forms` 개체의 속성을 다르게 처리 하 고 `Is` 또는 `IsNot` 연산자가 해당 값을 변경 하지 않고 속성의 상태를 확인할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>

## <a name="example"></a><span data-ttu-id="c58ef-131">예제</span><span class="sxs-lookup"><span data-stu-id="c58ef-131">Example</span></span>

<span data-ttu-id="c58ef-132">이 예에서는 기본 `SidebarMenu` 폼의 제목을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-132">This example changes the title of the default `SidebarMenu` form.</span></span>

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

<span data-ttu-id="c58ef-133">이 예제가 작동 하려면 프로젝트에 `SidebarMenu`라는 양식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>

<span data-ttu-id="c58ef-134">이 코드는 Windows 응용 프로그램 프로젝트 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c58ef-134">This code will work only in a Windows Application project.</span></span>

## <a name="requirements"></a><span data-ttu-id="c58ef-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c58ef-135">Requirements</span></span>

### <a name="availability-by-project-type"></a><span data-ttu-id="c58ef-136">프로젝트 형식에 따라 가용성</span><span class="sxs-lookup"><span data-stu-id="c58ef-136">Availability by Project Type</span></span>

|<span data-ttu-id="c58ef-137">프로젝트 형식</span><span class="sxs-lookup"><span data-stu-id="c58ef-137">Project type</span></span>|<span data-ttu-id="c58ef-138">사용 가능</span><span class="sxs-lookup"><span data-stu-id="c58ef-138">Available</span></span>|
|---|---|
|<span data-ttu-id="c58ef-139">Windows 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c58ef-139">Windows Application</span></span>|<span data-ttu-id="c58ef-140">**예**</span><span class="sxs-lookup"><span data-stu-id="c58ef-140">**Yes**</span></span>|
|<span data-ttu-id="c58ef-141">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c58ef-141">Class Library</span></span>|<span data-ttu-id="c58ef-142">아니요</span><span class="sxs-lookup"><span data-stu-id="c58ef-142">No</span></span>|
|<span data-ttu-id="c58ef-143">콘솔 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="c58ef-143">Console Application</span></span>|<span data-ttu-id="c58ef-144">아니요</span><span class="sxs-lookup"><span data-stu-id="c58ef-144">No</span></span>|
|<span data-ttu-id="c58ef-145">Windows 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c58ef-145">Windows Control Library</span></span>|<span data-ttu-id="c58ef-146">아니요</span><span class="sxs-lookup"><span data-stu-id="c58ef-146">No</span></span>|
|<span data-ttu-id="c58ef-147">웹 컨트롤 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c58ef-147">Web Control Library</span></span>|<span data-ttu-id="c58ef-148">아니요</span><span class="sxs-lookup"><span data-stu-id="c58ef-148">No</span></span>|
|<span data-ttu-id="c58ef-149">Windows 서비스</span><span class="sxs-lookup"><span data-stu-id="c58ef-149">Windows Service</span></span>|<span data-ttu-id="c58ef-150">아니요</span><span class="sxs-lookup"><span data-stu-id="c58ef-150">No</span></span>|
|<span data-ttu-id="c58ef-151">웹 사이트</span><span class="sxs-lookup"><span data-stu-id="c58ef-151">Web Site</span></span>|<span data-ttu-id="c58ef-152">아니요</span><span class="sxs-lookup"><span data-stu-id="c58ef-152">No</span></span>|

## <a name="see-also"></a><span data-ttu-id="c58ef-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c58ef-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="c58ef-154">개체</span><span class="sxs-lookup"><span data-stu-id="c58ef-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="c58ef-155">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="c58ef-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="c58ef-156">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="c58ef-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="c58ef-157">애플리케이션 폼 액세스</span><span class="sxs-lookup"><span data-stu-id="c58ef-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
