---
title: '방법: 개체 (Visual Basic)의 멤버에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: de00e428cc3d9d7a5688e853b0ff4295fec5b3e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322760"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="63410-102">방법: 개체 (Visual Basic)의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="63410-102">How to: Access Members of an Object (Visual Basic)</span></span>
<span data-ttu-id="63410-103">개체 변수에 개체를 참조 하는 경우, 해당 메서드, 속성, 필드 및 이벤트와 같은 경우 해당 개체의 멤버를 사용 하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="63410-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="63410-104">예를 들어 만든 후 새 <xref:System.Windows.Forms.Form> 개체를 설정 하려는 경우 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성 또는 호출 해당 <xref:System.Windows.Forms.Control.Focus%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="63410-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>  
  
## <a name="accessing-members"></a><span data-ttu-id="63410-105">멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="63410-105">Accessing Members</span></span>  
 <span data-ttu-id="63410-106">참조 하는 변수를 통해 개체의 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63410-106">You access an object's members through the variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="63410-107">개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="63410-107">To access members of an object</span></span>  
  
-   <span data-ttu-id="63410-108">멤버 액세스 연산자를 사용 하 여 (`.`) 간의 개체 변수 이름과 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63410-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     <span data-ttu-id="63410-109">멤버 이면 [공유](../../../../visual-basic/language-reference/modifiers/shared.md), 변수를 액세스할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63410-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>  
  
## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="63410-110">알려진 형식의 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="63410-110">Accessing Members of an Object of Known Type</span></span>  
 <span data-ttu-id="63410-111">컴파일 타임에 개체의 형식을 알고 있는 경우 사용할 수 있습니다 *초기 바인딩* 참조 하는 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="63410-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="63410-112">유형을 컴파일 시간에 알 수 있는 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="63410-112">To access members of an object for which you know the type at compile time</span></span>  
  
1. <span data-ttu-id="63410-113">변수에 할당 하려는 개체의 형식으로 개체 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="63410-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     <span data-ttu-id="63410-114">사용 하 여 `Option Strict On`에 할당할 수 있습니다 <xref:System.Windows.Forms.Form> 개체 (에서 파생 된 형식의 개체 또는 <xref:System.Windows.Forms.Form>)를 `extraForm`입니다.</span><span class="sxs-lookup"><span data-stu-id="63410-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="63410-115">클래스 또는 구조체를 확대 정의한 경우 `CType` 변환할 <xref:System.Windows.Forms.Form>, 해당 클래스를 할당 하거나 구조체 수도 `extraForm`합니다.</span><span class="sxs-lookup"><span data-stu-id="63410-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>  
  
2. <span data-ttu-id="63410-116">멤버 액세스 연산자를 사용 하 여 (`.`) 간의 개체 변수 이름과 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63410-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    extraForm.Show()  
    ```  
  
     <span data-ttu-id="63410-117">모든 메서드 및 속성에 액세스할 수 있습니다는 <xref:System.Windows.Forms.Form> 무엇이 든 간에 클래스는 `Option Strict` 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63410-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="63410-118">알 수 없는 형식의 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="63410-118">Accessing Members of an Object of Unknown Type</span></span>  
 <span data-ttu-id="63410-119">컴파일 타임에 개체의 형식을 알지 못하는 경우 사용 해야 *런타임에 바인딩* 참조 하는 모든 변수에 대해 합니다.</span><span class="sxs-lookup"><span data-stu-id="63410-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="63410-120">모르는 형식이 컴파일 타임에 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="63410-120">To access members of an object for which you do not know the type at compile time</span></span>  
  
1. <span data-ttu-id="63410-121">개체 변수를 선언 합니다 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63410-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="63410-122">(으로 변수 선언 `Object` 으로 선언 하는 것과 같습니다 <xref:System.Object?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="63410-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>  
  
    ```  
    Dim someControl As Object  
    ```  
  
     <span data-ttu-id="63410-123">사용 하 여 `Option Strict On`에 정의 된 멤버에만 액세스할 수 있습니다는 <xref:System.Object> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="63410-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>  
  
2. <span data-ttu-id="63410-124">멤버 액세스 연산자를 사용 하 여 (`.`) 간의 개체 변수 이름과 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63410-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    someControl.GetType()  
    ```  
  
     <span data-ttu-id="63410-125">개체 변수에 할당 하는 모든 개체의 멤버에 액세스할 수를 설정 해야 `Option Strict Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="63410-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="63410-126">이렇게 하면 컴파일러는 개체를 변수에 할당 하 여 지정된 된 멤버 노출 된다는 것을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63410-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="63410-127">개체에 액세스 하려는 멤버를 노출 하지 않습니다 경우는 <xref:System.MemberAccessException> 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="63410-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63410-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="63410-128">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="63410-129">개체 변수</span><span class="sxs-lookup"><span data-stu-id="63410-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="63410-130">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="63410-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="63410-131">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="63410-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="63410-132">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="63410-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
