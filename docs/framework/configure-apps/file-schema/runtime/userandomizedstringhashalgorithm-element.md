---
title: <UseRandomizedStringHashAlgorithm> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153779"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="74593-102">\<사용임의적 스트링해시 알고리즘> 요소</span><span class="sxs-lookup"><span data-stu-id="74593-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="74593-103">공통 언어 런타임이 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
<span data-ttu-id="74593-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="74593-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="74593-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="74593-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="74593-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<사용임의적 스트링해시 알고리즘>**</span><span class="sxs-lookup"><span data-stu-id="74593-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74593-107">구문</span><span class="sxs-lookup"><span data-stu-id="74593-107">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74593-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="74593-108">Attributes and Elements</span></span>  
 <span data-ttu-id="74593-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74593-110">특성</span><span class="sxs-lookup"><span data-stu-id="74593-110">Attributes</span></span>  
  
|<span data-ttu-id="74593-111">attribute</span><span class="sxs-lookup"><span data-stu-id="74593-111">Attribute</span></span>|<span data-ttu-id="74593-112">Description</span><span class="sxs-lookup"><span data-stu-id="74593-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="74593-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="74593-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="74593-114">문자열에 대한 해시 코드가 응용 프로그램 도메인별로 계산되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-114">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="74593-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="74593-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="74593-116">값</span><span class="sxs-lookup"><span data-stu-id="74593-116">Value</span></span>|<span data-ttu-id="74593-117">Description</span><span class="sxs-lookup"><span data-stu-id="74593-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="74593-118">공통 언어 런타임은 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산하지 않습니다. 단일 알고리즘은 문자열 해시 코드를 계산하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74593-118">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="74593-119">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="74593-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="74593-120">공통 언어 런타임은 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-120">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="74593-121">서로 다른 응용 프로그램 도메인과 다른 프로세스의 동일한 문자열에는 서로 다른 해시 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74593-121">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74593-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="74593-122">Child Elements</span></span>  
 <span data-ttu-id="74593-123">없음</span><span class="sxs-lookup"><span data-stu-id="74593-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74593-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="74593-124">Parent Elements</span></span>  
  
|<span data-ttu-id="74593-125">요소</span><span class="sxs-lookup"><span data-stu-id="74593-125">Element</span></span>|<span data-ttu-id="74593-126">Description</span><span class="sxs-lookup"><span data-stu-id="74593-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="74593-127">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74593-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="74593-128">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74593-129">설명</span><span class="sxs-lookup"><span data-stu-id="74593-129">Remarks</span></span>  
 <span data-ttu-id="74593-130">기본적으로 클래스와 <xref:System.StringComparer> 메서드는 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 응용 프로그램 도메인 간에 일관된 해시 코드를 생성하는 단일 해시 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-130">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="74593-131">이는 `enabled` `<UseRandomizedStringHashAlgorithm>` 요소의 특성을 에 설정하는 `0`것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74593-131">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="74593-132">.NET Framework 4에 사용되는 해싱 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="74593-132">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="74593-133">클래스와 <xref:System.StringComparer> <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 메서드는 응용 프로그램 도메인별로 해시 코드를 계산하는 다른 해시 알고리즘을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74593-133">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="74593-134">따라서 해당 문자열에 대한 해시 코드는 응용 프로그램 도메인마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="74593-134">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="74593-135">이 기능은 옵트인 기능입니다. 이를 활용하려면 요소의 특성을 `enabled` `<UseRandomizedStringHashAlgorithm>` `1`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-135">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="74593-136">해시 테이블의 문자열 조회는 일반적으로 O(1) 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="74593-136">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="74593-137">그러나 많은 수의 충돌이 발생하면 조회가<sup>O(n2)</sup>작업이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74593-137">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="74593-138">`<UseRandomizedStringHashAlgorithm>` 구성 요소를 사용하여 응용 프로그램 도메인당 임의의 해싱 알고리즘을 생성할 수 있으며, 특히 해시 코드가 계산되는 키가 사용자가 입력한 데이터를 기반으로 하는 경우 잠재적충돌 횟수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74593-138">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74593-139">예제</span><span class="sxs-lookup"><span data-stu-id="74593-139">Example</span></span>  
 <span data-ttu-id="74593-140">다음 예제에서는 "이 문자열은 문자열입니다"라는 값을 포함하는 전용 문자열 상수를 `DisplayString` `s`포함하는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-140">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="74593-141">메서드를 실행하는 애플리케이션 도메인의 이름과 함께 문자열 값 및 해시 코드를 표시하는 `ShowStringHashCode` 메서드도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-141">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="74593-142">구성 파일을 지정하지 않고 이 예제를 실행할 경우 다음과 유사한 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74593-142">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="74593-143">문자열의 해시 코드는 두 애플리케이션 도메인에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-143">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="74593-144">하지만 샘플 디렉터리에 다음의 구성을 추가하고 샘플을 실행하는 경우 동일 문자열의 해시 코드는 애플리케이션 도메인에 의해 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="74593-144">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="74593-145">구성 파일이 있는 경우 예제는 다음과 같은 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="74593-145">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="74593-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74593-146">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
