---
title: 필드 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: c00929ca499e39bd4e24d482c9413beb9cccddc1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741604"
---
# <a name="field-design"></a><span data-ttu-id="4fb95-102">필드 디자인</span><span class="sxs-lookup"><span data-stu-id="4fb95-102">Field Design</span></span>
<span data-ttu-id="4fb95-103">캡슐화의 원칙은 개체 지향 디자인에서 가장 중요 한 개념 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="4fb95-104">이 원칙은 개체 내에 저장 된 데이터에만 해당 개체에 액세스할 수 있음을 명시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>

 <span data-ttu-id="4fb95-105">원칙을 해석 하는 유용한 방법은 형식의 멤버 이외의 코드를 구분 하지 않고 해당 형식 (이름 또는 형식)의 필드에 대 한 변경 내용을 만들 수 있도록 형식을 디자인 해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="4fb95-106">이 해석은 즉시 모든 필드가 private 이어야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-106">This interpretation immediately implies that all fields must be private.</span></span>

 <span data-ttu-id="4fb95-107">이 엄격한 제한에서 상수 및 정적 읽기 전용 필드를 제외 합니다. 이러한 필드는 거의 정의가 아니므로 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>

 <span data-ttu-id="4fb95-108">공용 또는 보호 되는 인스턴스 필드를 제공 하지 ❌.</span><span class="sxs-lookup"><span data-stu-id="4fb95-108">❌ DO NOT provide instance fields that are public or protected.</span></span>

 <span data-ttu-id="4fb95-109">필드를 공용 또는 보호 하는 대신 필드에 액세스 하기 위한 속성을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>

 <span data-ttu-id="4fb95-110">✔️는 변경 되지 않는 상수에 상수 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-110">✔️ DO use constant fields for constants that will never change.</span></span>

 <span data-ttu-id="4fb95-111">컴파일러는 const 필드의 값을 호출 코드에 직접 굽습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="4fb95-112">따라서 호환성을 손상 시 키 지 않으면 서 const 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>

 <span data-ttu-id="4fb95-113">✔️는 미리 정의 된 개체 인스턴스에 대해 공용 정적 `readonly` 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-113">✔️ DO use public static `readonly` fields for predefined object instances.</span></span>

 <span data-ttu-id="4fb95-114">형식에 대 한 미리 정의 된 인스턴스가 있는 경우 형식 자체의 공용 읽기 전용 정적 필드로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>

 <span data-ttu-id="4fb95-115">❌ 변경할 수 있는 형식의 인스턴스를 `readonly` 필드에 할당 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-115">❌ DO NOT assign instances of mutable types to `readonly` fields.</span></span>

 <span data-ttu-id="4fb95-116">변경 가능한 형식은 인스턴스가 인스턴스화된 후 수정할 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="4fb95-117">예를 들어 배열, 대부분의 컬렉션 및 스트림은 변경 가능한 형식이 며 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>및 <xref:System.String?displayProperty=nameWithType>는 모두 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="4fb95-118">참조 형식 필드의 읽기 전용 한정자는 필드에 저장 된 인스턴스가 대체 되지 않도록 하지만 인스턴스를 변경 하는 멤버를 호출 하 여 필드의 인스턴스 데이터가 수정 되는 것을 방지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb95-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>

 <span data-ttu-id="4fb95-119">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="4fb95-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4fb95-120">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4fb95-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4fb95-121">참조</span><span class="sxs-lookup"><span data-stu-id="4fb95-121">See also</span></span>

- [<span data-ttu-id="4fb95-122">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4fb95-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="4fb95-123">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4fb95-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
