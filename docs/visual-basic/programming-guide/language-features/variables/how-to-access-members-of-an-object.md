---
description: '자세히 알아보기: 방법: 개체의 멤버에 액세스 (Visual Basic)'
title: '방법: 개체의 멤버에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: b4aed213bbe520b7b7027acc146d0973f7273fd1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435527"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="1716c-103">방법: 개체의 멤버에 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1716c-103">How to: Access Members of an Object (Visual Basic)</span></span>

<span data-ttu-id="1716c-104">개체를 참조 하는 개체 변수를 사용 하는 경우 해당 개체의 멤버 (예: 메서드, 속성, 필드 및 이벤트)로 작업 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-104">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="1716c-105">예를 들어 새 개체를 만든 후에는 <xref:System.Windows.Forms.Form> 해당 속성을 설정 <xref:System.Windows.Forms.Control.Text%2A> 하거나 메서드를 호출할 수 있습니다 <xref:System.Windows.Forms.Control.Focus%2A> .</span><span class="sxs-lookup"><span data-stu-id="1716c-105">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="1716c-106">멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="1716c-106">Accessing Members</span></span>

<span data-ttu-id="1716c-107">개체를 참조 하는 변수를 통해 개체의 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-107">You access an object's members through the variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="1716c-108">개체의 멤버에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="1716c-108">To access members of an object</span></span>

- <span data-ttu-id="1716c-109">`.`개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자 ()를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-109">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    currentText = newForm.Text
    ```

    <span data-ttu-id="1716c-110">멤버를 [공유](../../../language-reference/modifiers/shared.md)하는 경우 변수에 액세스할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-110">If the member is [Shared](../../../language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>

## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="1716c-111">알려진 형식 개체의 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="1716c-111">Accessing Members of an Object of Known Type</span></span>

<span data-ttu-id="1716c-112">컴파일 타임에 개체의 형식을 알고 있는 경우이를 참조 하는 변수에 대 한 *초기 바인딩을* 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-112">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="1716c-113">컴파일 타임에 형식을 알고 있는 개체의 멤버에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="1716c-113">To access members of an object for which you know the type at compile time</span></span>

1. <span data-ttu-id="1716c-114">변수에 할당 하려는 개체의 형식이 되도록 개체 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-114">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    <span data-ttu-id="1716c-115">를 사용 하 여 `Option Strict On` <xref:System.Windows.Forms.Form> 개체 (또는에서 파생 된 형식의 개체)만에 할당할 수 있습니다 <xref:System.Windows.Forms.Form> `extraForm` .</span><span class="sxs-lookup"><span data-stu-id="1716c-115">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="1716c-116">확대 변환으로 클래스 또는 구조체를 정의한 경우 `CType` <xref:System.Windows.Forms.Form> 해당 클래스 또는 구조체를에 할당할 수도 있습니다 `extraForm` .</span><span class="sxs-lookup"><span data-stu-id="1716c-116">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>

2. <span data-ttu-id="1716c-117">`.`개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자 ()를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-117">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    extraForm.Show()
    ```

    <span data-ttu-id="1716c-118">설정에 관계 없이 클래스와 관련 된 모든 메서드와 속성에 액세스할 수 있습니다 <xref:System.Windows.Forms.Form> `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="1716c-118">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>

## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="1716c-119">알 수 없는 형식의 개체 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="1716c-119">Accessing Members of an Object of Unknown Type</span></span>

<span data-ttu-id="1716c-120">컴파일 타임에 개체 형식을 알 수 없는 경우이를 참조 하는 모든 변수에 대해 *런타임에 바인딩을* 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-120">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="1716c-121">컴파일 타임에 형식을 알 수 없는 개체의 멤버에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="1716c-121">To access members of an object for which you do not know the type at compile time</span></span>

1. <span data-ttu-id="1716c-122">개체 변수를 [개체 데이터 형식](../../../language-reference/data-types/object-data-type.md)으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-122">Declare the object variable to be of the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="1716c-123">변수를로 선언 하는 것은로 선언 하는 것과 `Object` 같습니다 <xref:System.Object?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1716c-123">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>

    ```vb
    Dim someControl As Object
    ```

    <span data-ttu-id="1716c-124">`Option Strict On`에서는 클래스에 정의 된 멤버에만 액세스할 수 있습니다 <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="1716c-124">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>

2. <span data-ttu-id="1716c-125">`.`개체 변수 이름과 멤버 이름 사이에 멤버 액세스 연산자 ()를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-125">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    someControl.GetType()
    ```

    <span data-ttu-id="1716c-126">개체 변수에 할당 하는 개체의 멤버에 액세스할 수 있으려면를 설정 해야 합니다 `Option Strict Off` .</span><span class="sxs-lookup"><span data-stu-id="1716c-126">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="1716c-127">이 작업을 수행 하는 경우 컴파일러는 지정 된 멤버가 변수에 할당 한 개체에 의해 노출 되는 것을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-127">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="1716c-128">개체에서 액세스 하려는 멤버를 노출 하지 않는 경우 <xref:System.MemberAccessException> 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1716c-128">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="1716c-129">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1716c-129">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="1716c-130">개체 변수</span><span class="sxs-lookup"><span data-stu-id="1716c-130">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="1716c-131">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="1716c-131">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="1716c-132">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="1716c-132">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="1716c-133">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="1716c-133">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
