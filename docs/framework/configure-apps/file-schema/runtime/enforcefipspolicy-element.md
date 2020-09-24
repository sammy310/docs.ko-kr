---
title: <enforceFIPSPolicy> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: 864a371d4ad10585e672452ad85cc09d4b684068
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158840"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="fde84-102">\<enforceFIPSPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="fde84-102">\<enforceFIPSPolicy> Element</span></span>

<span data-ttu-id="fde84-103">암호화 알고리즘이 FIPS(Federal Information Processing Standards)를 준수해야 하는 컴퓨터 구성 요구 사항을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="fde84-104">구문</span><span class="sxs-lookup"><span data-stu-id="fde84-104">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fde84-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fde84-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fde84-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fde84-107">특성</span><span class="sxs-lookup"><span data-stu-id="fde84-107">Attributes</span></span>  
  
|<span data-ttu-id="fde84-108">attribute</span><span class="sxs-lookup"><span data-stu-id="fde84-108">Attribute</span></span>|<span data-ttu-id="fde84-109">설명</span><span class="sxs-lookup"><span data-stu-id="fde84-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fde84-110">사용</span><span class="sxs-lookup"><span data-stu-id="fde84-110">enabled</span></span>|<span data-ttu-id="fde84-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="fde84-112">암호화 알고리즘이 FIPS와 호환 되어야 하는 컴퓨터 구성 요구 사항을 적용 하도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-112">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="fde84-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="fde84-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="fde84-114">Value</span><span class="sxs-lookup"><span data-stu-id="fde84-114">Value</span></span>|<span data-ttu-id="fde84-115">설명</span><span class="sxs-lookup"><span data-stu-id="fde84-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="fde84-116">암호화 알고리즘을 FIPS 규격으로 요구 하도록 컴퓨터를 구성한 경우에는 해당 요구 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-116">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="fde84-117">클래스가 FIPS와 호환 되지 않는 알고리즘을 구현 하는 경우 해당 `Create` 클래스에 대 한 생성자 또는 메서드는 해당 컴퓨터에서 실행 될 때 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-117">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="fde84-118">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="fde84-119">응용 프로그램에서 사용 하는 암호화 알고리즘은 컴퓨터 구성에 관계 없이 FIPS를 준수 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-119">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fde84-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fde84-120">Child Elements</span></span>  

 <span data-ttu-id="fde84-121">없음</span><span class="sxs-lookup"><span data-stu-id="fde84-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fde84-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fde84-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fde84-123">요소</span><span class="sxs-lookup"><span data-stu-id="fde84-123">Element</span></span>|<span data-ttu-id="fde84-124">설명</span><span class="sxs-lookup"><span data-stu-id="fde84-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fde84-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="fde84-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fde84-127">설명</span><span class="sxs-lookup"><span data-stu-id="fde84-127">Remarks</span></span>  

 <span data-ttu-id="fde84-128">2.0 .NET Framework부터 암호화 알고리즘을 구현 하는 클래스를 만드는 것은 컴퓨터의 구성에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-128">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="fde84-129">컴퓨터가 FIPS와 호환 되지 않는 알고리즘을 요구 하도록 구성 되어 있고 클래스가 FIPS와 호환 되지 않는 알고리즘을 구현 하는 경우 해당 클래스의 인스턴스를 만들려고 하면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-129">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="fde84-130">생성자는 <xref:System.InvalidOperationException> 예외를 throw 하 고 `Create` 메서드는 <xref:System.Reflection.TargetInvocationException> 내부 예외를 사용 하 여 예외를 throw <xref:System.InvalidOperationException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-130">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="fde84-131">구성에서 fips를 준수 해야 하는 컴퓨터에서 응용 프로그램이 실행 되 고 응용 프로그램에서 FIPS와 호환 되지 않는 알고리즘을 사용 하는 경우 구성 파일에서이 요소를 사용 하 여 CLR (공용 언어 런타임)에서 FIPS 준수를 적용 하지 않도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-131">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="fde84-132">이 요소는 .NET Framework 2.0 서비스 팩 1에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-132">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fde84-133">예제</span><span class="sxs-lookup"><span data-stu-id="fde84-133">Example</span></span>  

 <span data-ttu-id="fde84-134">다음 예제에서는 CLR에서 FIPS 준수를 적용 하지 않도록 방지 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fde84-134">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fde84-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fde84-135">See also</span></span>

- [<span data-ttu-id="fde84-136">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fde84-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fde84-137">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="fde84-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fde84-138">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="fde84-138">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
