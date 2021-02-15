---
description: '자세한 정보: 필드 디자인'
title: 필드 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 88df60c3050035221dc65429bbd543c71d5d69b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642047"
---
# <a name="field-design"></a><span data-ttu-id="c9358-103">필드 디자인</span><span class="sxs-lookup"><span data-stu-id="c9358-103">Field Design</span></span>

<span data-ttu-id="c9358-104">캡슐화의 원칙은 개체 지향 디자인에서 가장 중요한 개념 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-104">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="c9358-105">이 원칙에 따르면 개체 내에 저장된 데이터에는 해당 개체만 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-105">This principle states that data stored inside an object should be accessible only to that object.</span></span>

 <span data-ttu-id="c9358-106">이 원칙은 형식의 멤버에 대한 코드 이외의 코드를 중단하지 않고 해당 형식의 필드를 변경(이름 또는 형식 변경)할 수 있도록 형식을 디자인해야 한다는 의미로 해석하는 것이 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-106">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="c9358-107">이 해석은 곧 모든 필드가 프라이빗이어야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-107">This interpretation immediately implies that all fields must be private.</span></span>

 <span data-ttu-id="c9358-108">상수 및 정적 읽기 전용 필드와 같은 필드는 정의에 따라 변경할 필요가 없기 때문에 이 엄격한 제한에서 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-108">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>

 <span data-ttu-id="c9358-109">❌ 퍼블릭이거나 보호된 인스턴스 필드를 제공하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c9358-109">❌ DO NOT provide instance fields that are public or protected.</span></span>

 <span data-ttu-id="c9358-110">퍼블릭 또는 보호된 필드로 설정하는 속성 대신 필드에 액세스하기 위한 속성을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-110">You should provide properties for accessing fields instead of making them public or protected.</span></span>

 <span data-ttu-id="c9358-111">✔️ 변경되지 않는 상수에는 상수 필드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c9358-111">✔️ DO use constant fields for constants that will never change.</span></span>

 <span data-ttu-id="c9358-112">컴파일러는 const 필드의 값을 호출 코드에 직접 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-112">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="c9358-113">따라서 호환성을 손상하지 않고 const 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-113">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>

 <span data-ttu-id="c9358-114">✔️ 미리 정의된 개체 인스턴스에 퍼블릭 정적 `readonly` 필드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c9358-114">✔️ DO use public static `readonly` fields for predefined object instances.</span></span>

 <span data-ttu-id="c9358-115">형식의 미리 정의된 인스턴스가 있는 경우 형식 자체의 퍼블릭 읽기 전용 정적 필드로 선언하세요.</span><span class="sxs-lookup"><span data-stu-id="c9358-115">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>

 <span data-ttu-id="c9358-116">❌ 변경 가능한 형식의 인스턴스를 `readonly` 필드에 할당하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c9358-116">❌ DO NOT assign instances of mutable types to `readonly` fields.</span></span>

 <span data-ttu-id="c9358-117">변경 가능한 형식은 인스턴스화된 후 수정할 수 있는 인스턴스가 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-117">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="c9358-118">예를 들어 배열, 대부분의 컬렉션, 스트림은 변경 가능한 형식이지만 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>은 모두 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-118">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="c9358-119">참조 형식 필드의 읽기 전용 한정자는 필드에 저장된 인스턴스를 대체할 수 없도록 하지만 인스턴스를 변경하는 멤버를 호출하여 필드의 인스턴스 데이터를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9358-119">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>

 <span data-ttu-id="c9358-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="c9358-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="c9358-121">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="c9358-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="c9358-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9358-122">See also</span></span>

- [<span data-ttu-id="c9358-123">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="c9358-123">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="c9358-124">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="c9358-124">Framework Design Guidelines</span></span>](index.md)
