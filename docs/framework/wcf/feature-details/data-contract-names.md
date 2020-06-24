---
title: 데이터 계약 이름
description: 동일한 데이터 계약을 사용 하 여 통신을 지 원하는 WCF 인프라의 기본 동작 및 데이터 계약을 검색 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], naming
ms.assetid: 31f87e6c-247b-48f5-8e94-b9e1e33d8d09
ms.openlocfilehash: 85c533d683558520d46f259db0bdb34dcb1214c9
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247405"
---
# <a name="data-contract-names"></a><span data-ttu-id="50036-103">데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="50036-103">Data Contract Names</span></span>

<span data-ttu-id="50036-104">때때로 클라이언트와 서비스는 동일한 형식을 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-104">Sometimes a client and a service do not share the same types.</span></span> <span data-ttu-id="50036-105">그래도 양쪽의 데이터 계약이 동일하면 서로 데이터를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-105">They can still pass data to each other as long as the data contracts are equivalent on both sides.</span></span> <span data-ttu-id="50036-106">데이터 [계약의 동등성](data-contract-equivalence.md) 은 데이터 계약 및 데이터 멤버 이름을 기반으로 하므로 형식 및 멤버를 해당 이름에 매핑하는 메커니즘이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50036-106">[Data Contract Equivalence](data-contract-equivalence.md) is based on data contract and data member names, and therefore a mechanism is provided to map types and members to those names.</span></span> <span data-ttu-id="50036-107">이 항목에서는 이름을 만들 때 WCF (Windows Communication Foundation) 인프라의 기본 동작 뿐만 아니라 데이터 계약의 이름을 지정 하는 규칙에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-107">This topic explains the rules for naming data contracts as well as the default behavior of the Windows Communication Foundation (WCF) infrastructure when creating names.</span></span>

## <a name="basic-rules"></a><span data-ttu-id="50036-108">기본 규칙</span><span class="sxs-lookup"><span data-stu-id="50036-108">Basic Rules</span></span>
<span data-ttu-id="50036-109">데이터 계약 이름 지정과 관련된 기본 규칙에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50036-109">Basic rules regarding naming data contracts include:</span></span>

- <span data-ttu-id="50036-110">정규화된 데이터 계약 이름은 네임스페이스와 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="50036-110">A fully-qualified data contract name consists of a namespace and a name.</span></span>

- <span data-ttu-id="50036-111">데이터 멤버에는 이름만 있으며, 네임스페이스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-111">Data members have only names, but no namespaces.</span></span>

- <span data-ttu-id="50036-112">데이터 계약을 처리할 때 WCF 인프라는 네임 스페이스와 데이터 계약 및 데이터 멤버의 이름에 대 한 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-112">When processing data contracts, the WCF infrastructure is case-sensitive to both the namespaces and the names of data contracts and data members.</span></span>

## <a name="data-contract-namespaces"></a><span data-ttu-id="50036-113">데이터 계약 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="50036-113">Data Contract Namespaces</span></span>
<span data-ttu-id="50036-114">데이터 계약 네임스페이스는 URI(Uniform Resource Identifier)의 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-114">A data contract namespace takes the form of a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="50036-115">절대 URI나 상대 URI일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-115">The URI can be either absolute or relative.</span></span> <span data-ttu-id="50036-116">기본적으로 특정 형식에 대한 데이터 계약은 해당 형식의 CLR(공용 언어 런타임) 네임스페이스로부터 가져오는 네임스페이스에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="50036-116">By default, data contracts for a particular type are assigned a namespace that comes from the common language runtime (CLR) namespace of that type.</span></span>

<span data-ttu-id="50036-117">기본적으로 *clr*네임 스페이스 형식의 지정 된 clr 네임 스페이스는 네임 스페이스에 매핑됩니다 `http://schemas.datacontract.org/2004/07/Clr.Namespace` .</span><span class="sxs-lookup"><span data-stu-id="50036-117">By default, any given CLR namespace (in the format *Clr.Namespace*) is mapped to the namespace `http://schemas.datacontract.org/2004/07/Clr.Namespace`.</span></span> <span data-ttu-id="50036-118">이 기본값을 재정의하려면 전체 모듈 또는 어셈블리에 <xref:System.Runtime.Serialization.ContractNamespaceAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-118">To override this default, apply the <xref:System.Runtime.Serialization.ContractNamespaceAttribute> attribute to the entire module or assembly.</span></span> <span data-ttu-id="50036-119">또는 각 형식에 대해 데이터 계약 네임스페이스를 제어하려면 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>의 <xref:System.Runtime.Serialization.DataContractAttribute> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-119">Alternatively, to control the data contract namespace for each type, set the <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> property of the <xref:System.Runtime.Serialization.DataContractAttribute>.</span></span>

> [!NOTE]
> <span data-ttu-id="50036-120">`http://schemas.microsoft.com/2003/10/Serialization`네임 스페이스는 예약 되어 있으므로 데이터 계약 네임 스페이스로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-120">The `http://schemas.microsoft.com/2003/10/Serialization` namespace is reserved and cannot be used as a data contract namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="50036-121">`delegate` 선언을 포함하는 데이터 계약 형식에서 기본 네임스페이스를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-121">You cannot override the default namespace in data contract types that contain `delegate` declarations.</span></span>

## <a name="data-contract-names"></a><span data-ttu-id="50036-122">데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="50036-122">Data Contract Names</span></span>
<span data-ttu-id="50036-123">주어진 형식에 대한 데이터 계약의 기본 이름은 해당 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50036-123">The default name of a data contract for a given type is the name of that type.</span></span> <span data-ttu-id="50036-124">기본값을 재정의하려면 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>의 <xref:System.Runtime.Serialization.DataContractAttribute> 속성을 대체 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-124">To override the default, set the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataContractAttribute> to an alternative name.</span></span> <span data-ttu-id="50036-125">제네릭 형식에 대한 특정 규칙은 이 항목의 뒷부분에 있는 "제네릭 형식에 대한 데이터 계약 이름"에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-125">Special rules for generic types are described in "Data Contract Names for Generic Types" later in this topic.</span></span>

## <a name="data-member-names"></a><span data-ttu-id="50036-126">데이터 멤버 이름</span><span class="sxs-lookup"><span data-stu-id="50036-126">Data Member Names</span></span>
<span data-ttu-id="50036-127">주어진 필드 또는 속성에 대한 데이터 멤버의 기본 이름은 해당 필드 또는 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50036-127">The default name of a data member for a given field or property is the name of that field or property.</span></span> <span data-ttu-id="50036-128">기본값을 재정의하려면 <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 대체 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-128">To override the default, set the <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> to an alternative value.</span></span>

### <a name="examples"></a><span data-ttu-id="50036-129">예제</span><span class="sxs-lookup"><span data-stu-id="50036-129">Examples</span></span>
<span data-ttu-id="50036-130">다음 예제에서는 데이터 계약 및 데이터 멤버의 기본 이름 지정 동작을 재정의할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50036-130">The following example shows how you can override the default naming behavior of data contracts and data members.</span></span>

[!code-csharp[C_DataContractNames#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#1)]
[!code-vb[C_DataContractNames#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#1)]

## <a name="data-contract-names-for-generic-types"></a><span data-ttu-id="50036-131">제네릭 형식에 대한 데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="50036-131">Data Contract Names for Generic Types</span></span>
<span data-ttu-id="50036-132">제네릭 형식에 대한 데이터 계약 이름을 결정하는 데 특별한 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-132">Special rules exist for determining data contract names for generic types.</span></span> <span data-ttu-id="50036-133">이러한 규칙은 동일한 제네릭 형식의 폐쇄형 두 개의 제네릭 형식 간에 데이터 계약 이름이 충돌하는 것을 막도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="50036-133">These rules help avoid data contract name collisions between two closed generics of the same generic type.</span></span>

<span data-ttu-id="50036-134">기본적으로 제네릭 형식에 대 한 데이터 계약 이름은 형식 이름 뒤에 문자열 "Of", 제네릭 매개 변수의 데이터 계약 이름, 제네릭 매개 변수의 데이터 계약 네임 스페이스를 사용 하 여 계산 된 *해시가* 차례로 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="50036-134">By default, the data contract name for a generic type is the name of the type, followed by the string "Of", followed by the data contract names of the generic parameters, followed by a *hash* computed using the data contract namespaces of the generic parameters.</span></span> <span data-ttu-id="50036-135">해시는 데이터 조각을 고유하게 식별하는 "지문"의 역할을 하는 수학 함수의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="50036-135">A hash is the result of a mathematical function that acts as a "fingerprint" that uniquely identifies a piece of data.</span></span> <span data-ttu-id="50036-136">모든 제네릭 매개 변수가 기본 형식인 경우 해시는 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="50036-136">When all of the generic parameters are primitive types, the hash is omitted.</span></span>

<span data-ttu-id="50036-137">예를 들어 다음 예제의 형식을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="50036-137">For example, see the types in the following example.</span></span>

[!code-csharp[C_DataContractNames#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#2)]
[!code-vb[C_DataContractNames#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#2)]

<span data-ttu-id="50036-138">이 예제에서 `Drawing<Square,RegularRedBrush>` 형식의 데이터 계약 이름은 "DrawingOfSquareRedBrush5HWGAU6h"이며, 여기서 "5HWGAU6h"는 "urn:shapes" 및 "urn:default" 네임스페이스의 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="50036-138">In this example, the type `Drawing<Square,RegularRedBrush>` has the data contract name "DrawingOfSquareRedBrush5HWGAU6h", where "5HWGAU6h" is a hash of the "urn:shapes" and "urn:default" namespaces.</span></span> <span data-ttu-id="50036-139">`Drawing<Square,SpecialRedBrush>` 형식의 데이터 계약 이름은 "DrawingOfSquareRedBrushjpB5LgQ_S"이며, 여기서 "jpB5LgQ_S"는 "urn:shapes" 및 "urn:special" 네임스페이스의 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="50036-139">The type `Drawing<Square,SpecialRedBrush>` has the data contract name "DrawingOfSquareRedBrushjpB5LgQ_S", where "jpB5LgQ_S" is a hash of the "urn:shapes" and the "urn:special" namespaces.</span></span> <span data-ttu-id="50036-140">해시를 사용하지 않으면 두 이름이 동일하므로 이름이 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="50036-140">Note that if the hash is not used, the two names are identical, and thus a name collision occurs.</span></span>

## <a name="customizing-data-contract-names-for-generic-types"></a><span data-ttu-id="50036-141">제네릭 형식에 대 한 데이터 계약 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="50036-141">Customizing data contract names for generic types</span></span>

<span data-ttu-id="50036-142">위에서 설명한 것과 같이 제네릭 형식에 대해 생성된 데이터 계약 이름이 허용되지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-142">Sometimes, the data contract names generated for generic types, as described previously, are unacceptable.</span></span> <span data-ttu-id="50036-143">예를 들어 이름 충돌이 발생하지 않도록 하려면 해시를 제거해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-143">For example, you may know in advance that you will not run into name collisions and may want to remove the hash.</span></span> <span data-ttu-id="50036-144">이 경우 속성을 사용 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A?displayProperty=nameWithType> 하 여 이름을 생성 하는 다른 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-144">In this case, you can use the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A?displayProperty=nameWithType> property to specify a different way to generate names.</span></span> <span data-ttu-id="50036-145">제네릭 매개 변수의 데이터 계약 이름을 참조하기 위해 `Name` 속성 내에서 중괄호 안에 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-145">You can use numbers in curly braces inside of the `Name` property to refer to data contract names of the generic parameters.</span></span> <span data-ttu-id="50036-146">0은 첫 번째 매개 변수를 참조 하 고, 1은 두 번째 매개 변수를 참조 합니다. 중괄호 안의 숫자 (#) 기호를 사용 하 여 해시를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-146">(0 refers to the first parameter, 1 refers to the second, and so on.) You can use a number (#) sign inside curly braces to refer to the hash.</span></span> <span data-ttu-id="50036-147">이러한 각각의 참조를 여러 번 사용하거나 전혀 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-147">You can use each of these references multiple times or not at all.</span></span>

<span data-ttu-id="50036-148">예를 들어 이전 제네릭 `Drawing` 형식은 다음 예제와 같이 선언되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-148">For example, the preceding generic `Drawing` type could have been declared as shown in the following example.</span></span>

[!code-csharp[c_DataContractNames#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#3)]
[!code-vb[c_DataContractNames#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#3)]

<span data-ttu-id="50036-149">이 경우에는 `Drawing<Square,RegularRedBrush>` 형식의 데이터 계약 이름이 "Drawing_using_RedBrush_brush_and_Square_shape"입니다.</span><span class="sxs-lookup"><span data-stu-id="50036-149">In this case, the type `Drawing<Square,RegularRedBrush>` has the data contract name "Drawing_using_RedBrush_brush_and_Square_shape".</span></span> <span data-ttu-id="50036-150"><xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> 속성에 "{#}"이 있으면 해시가 이름의 일부가 아니므로 형식의 이름을 지정할 때 충돌이 발생하기 쉽습니다. 예를 들어 `Drawing<Square,SpecialRedBrush>` 형식의 데이터 계약 이름이 동일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50036-150">Note that because there is a "{#}" in the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> property, the hash is not a part of the name, and thus the type is susceptible to naming collisions; for example, the type `Drawing<Square,SpecialRedBrush>` would have exactly the same data contract name.</span></span>

## <a name="see-also"></a><span data-ttu-id="50036-151">참조</span><span class="sxs-lookup"><span data-stu-id="50036-151">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.ContractNamespaceAttribute>
- [<span data-ttu-id="50036-152">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="50036-152">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="50036-153">데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="50036-153">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="50036-154">데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="50036-154">Data Contract Names</span></span>](data-contract-names.md)
- [<span data-ttu-id="50036-155">데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="50036-155">Data Contract Versioning</span></span>](data-contract-versioning.md)
