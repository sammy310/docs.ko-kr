---
title: 필드 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 3ab8fe279605c4795bb3a26557d0241b186b273a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026408"
---
# <a name="field-design"></a><span data-ttu-id="272d4-102">필드 디자인</span><span class="sxs-lookup"><span data-stu-id="272d4-102">Field Design</span></span>
<span data-ttu-id="272d4-103">캡슐화의 원리는 개체 지향 디자인의 가장 중요 한 개념 중 하나를입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="272d4-104">개체 내에 저장 된 데이터 개체에만 액세스할 수 있는 되도록 하는 것이 원칙입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="272d4-105">형식 (이름 또는 형식 변경) 해당 형식의 필드에 변경 내용을 형식의 멤버에 대 한 다른 코드를 중단 하지 않고 적용할 수 있도록 디자인 해야는 예를 들어 방법은 하는 원칙을 해석 하는 유용한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="272d4-106">이 해석을 즉시 모든 필드를 private 이어야 합니다을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="272d4-107">이러한 필드 정의 따라 거의 필요가 없으며 변경 때문에 상수 및 정적 읽기 전용 필드가 엄격한 제한에서 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="272d4-108">**X DO NOT** 공용 또는 보호 되는 인스턴스 필드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="272d4-109">Public 또는 protected 있도록 대신 필드에 액세스 하기 위한 속성을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="272d4-110">**✓ DO** 상수 필드는 변경 되지 않는 상수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="272d4-111">컴파일러는 호출 코드에 직접 const 필드의 값을 굽습니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="272d4-112">따라서 상수 값의 호환성을 손상 위험 없이 되지 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="272d4-113">**✓ DO** 공용 정적을 사용 하 여 `readonly` 미리 정의 된 개체 인스턴스에 대 한 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="272d4-114">미리 정의 된 형식 인스턴스의 경우 공용으로 읽기 전용 정적 필드 형식 자체의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="272d4-115">**X DO NOT** 변경할 수 있는 형식의 인스턴스를 할당할 `readonly` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="272d4-116">변경 가능한 형식은 인스턴스화되는 후 수정할 수 있는 인스턴스를 사용 하 여 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="272d4-117">예를 들어, 배열, 대부분의 컬렉션 및 스트림 유형은 변경할 수 있는, 하지만 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, 및 <xref:System.String?displayProperty=nameWithType> 는 모두 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="272d4-118">참조 형식 필드에 read-only 한정자 교체 중인 필드에 저장 된 인스턴스 수 없지만 필드의 인스턴스 데이터 인스턴스 변경 멤버를 호출 하 여 수정 되지 않도록 방지 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="272d4-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="272d4-119">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="272d4-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="272d4-120">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="272d4-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="272d4-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="272d4-121">See also</span></span>

- [<span data-ttu-id="272d4-122">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="272d4-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="272d4-123">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="272d4-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
