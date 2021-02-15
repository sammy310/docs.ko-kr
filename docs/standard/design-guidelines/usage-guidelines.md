---
description: '자세한 정보: 사용 지침'
title: 사용 지침
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: a435fab2adb00f671dfde1619a3c1f8db719d9df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641800"
---
# <a name="usage-guidelines"></a><span data-ttu-id="a62bb-103">사용 지침</span><span class="sxs-lookup"><span data-stu-id="a62bb-103">Usage guidelines</span></span>

<span data-ttu-id="a62bb-104">이 섹션에서는 공개적으로 액세스할 수 있는 API에서 공용 형식을 사용하는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a62bb-104">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="a62bb-105">기본 제공 프레임워크 형식(예: serialization 특성)의 직접 사용 및 일반 연산자 오버로드에 대해서도 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="a62bb-105">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="a62bb-106"><xref:System.IDisposable?displayProperty=nameWithType> 인터페이스는 이 섹션에서 다루지 않고 [Dispose 패턴](../garbage-collection/implementing-dispose.md) 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a62bb-106">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="a62bb-107">기타 기본 제공되는 .NET Framework 공용 형식에 대한 지침 및 추가 정보는 <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>에 대한 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a62bb-107">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a62bb-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a62bb-108">In this section</span></span>

[<span data-ttu-id="a62bb-109">배열</span><span class="sxs-lookup"><span data-stu-id="a62bb-109">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="a62bb-110">특성</span><span class="sxs-lookup"><span data-stu-id="a62bb-110">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="a62bb-111">컬렉션</span><span class="sxs-lookup"><span data-stu-id="a62bb-111">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="a62bb-112">serialization</span><span class="sxs-lookup"><span data-stu-id="a62bb-112">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="a62bb-113">System.Xml 사용법</span><span class="sxs-lookup"><span data-stu-id="a62bb-113">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="a62bb-114">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="a62bb-114">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="a62bb-115">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="a62bb-115">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="a62bb-116">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="a62bb-116">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a62bb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a62bb-117">See also</span></span>

- [<span data-ttu-id="a62bb-118">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a62bb-118">Framework Design Guidelines</span></span>](index.md)
