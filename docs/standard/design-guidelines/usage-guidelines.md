---
title: 사용 지침
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: d6ea7c7b9ada95e3d0c425aaea18be6cdbb4ce35
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828506"
---
# <a name="usage-guidelines"></a><span data-ttu-id="e0c87-102">사용 지침</span><span class="sxs-lookup"><span data-stu-id="e0c87-102">Usage guidelines</span></span>

<span data-ttu-id="e0c87-103">이 섹션에는 공개적으로 액세스할 수 있는 Api에서 공용 형식을 사용 하기 위한 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c87-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="e0c87-104">기본 제공 프레임 워크 형식 (예: serialization 특성)을 직접 사용 하 고 일반적인 연산자를 오버 로드 하는 방법을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="e0c87-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="e0c87-105"><xref:System.IDisposable?displayProperty=nameWithType>이 단원에서는이 인터페이스에 대해 다루지 않지만 [삭제 패턴](../garbage-collection/implementing-dispose.md) 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c87-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="e0c87-106">일반적인 기본 제공 .NET Framework 형식에 대 한 지침 및 추가 정보는,,,,,,,에 대 한 참조 항목을 참조 하세요. <xref:System.DateTime?displayProperty=nameWithType> <xref:System.DateTimeOffset?displayProperty=nameWithType> <xref:System.ICloneable?displayProperty=nameWithType> <xref:System.IComparable%601?displayProperty=nameWithType> <xref:System.IEquatable%601?displayProperty=nameWithType> <xref:System.Nullable%601?displayProperty=nameWithType> <xref:System.Object?displayProperty=nameWithType> <xref:System.Uri?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e0c87-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e0c87-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e0c87-107">In this section</span></span>

[<span data-ttu-id="e0c87-108">배열</span><span class="sxs-lookup"><span data-stu-id="e0c87-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="e0c87-109">특성</span><span class="sxs-lookup"><span data-stu-id="e0c87-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="e0c87-110">컬렉션</span><span class="sxs-lookup"><span data-stu-id="e0c87-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="e0c87-111">serialization</span><span class="sxs-lookup"><span data-stu-id="e0c87-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="e0c87-112">System.Xml 사용</span><span class="sxs-lookup"><span data-stu-id="e0c87-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="e0c87-113">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="e0c87-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="e0c87-114">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="e0c87-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="e0c87-115">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="e0c87-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e0c87-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0c87-116">See also</span></span>

- [<span data-ttu-id="e0c87-117">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="e0c87-117">Framework Design Guidelines</span></span>](index.md)
