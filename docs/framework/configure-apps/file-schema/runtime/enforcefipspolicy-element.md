---
description: '다음에 대 한 자세한 정보: <enforceFIPSPolicy> 요소'
title: <enforceFIPSPolicy> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: d445570db634867a15b6d97d4e20186bd0641c2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787073"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="c4617-103">\<enforceFIPSPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="c4617-103">\<enforceFIPSPolicy> Element</span></span>

<span data-ttu-id="c4617-104">암호화 알고리즘이 FIPS(Federal Information Processing Standards)를 준수해야 하는 컴퓨터 구성 요구 사항을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-104">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="c4617-105">구문</span><span class="sxs-lookup"><span data-stu-id="c4617-105">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4617-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c4617-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c4617-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4617-108">특성</span><span class="sxs-lookup"><span data-stu-id="c4617-108">Attributes</span></span>  
  
|<span data-ttu-id="c4617-109">attribute</span><span class="sxs-lookup"><span data-stu-id="c4617-109">Attribute</span></span>|<span data-ttu-id="c4617-110">설명</span><span class="sxs-lookup"><span data-stu-id="c4617-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4617-111">사용</span><span class="sxs-lookup"><span data-stu-id="c4617-111">enabled</span></span>|<span data-ttu-id="c4617-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="c4617-113">암호화 알고리즘이 FIPS와 호환 되어야 하는 컴퓨터 구성 요구 사항을 적용 하도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-113">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c4617-114">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c4617-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="c4617-115">값</span><span class="sxs-lookup"><span data-stu-id="c4617-115">Value</span></span>|<span data-ttu-id="c4617-116">설명</span><span class="sxs-lookup"><span data-stu-id="c4617-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="c4617-117">암호화 알고리즘을 FIPS 규격으로 요구 하도록 컴퓨터를 구성한 경우에는 해당 요구 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-117">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="c4617-118">클래스가 FIPS와 호환 되지 않는 알고리즘을 구현 하는 경우 해당 `Create` 클래스에 대 한 생성자 또는 메서드는 해당 컴퓨터에서 실행 될 때 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-118">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="c4617-119">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-119">This is the default.</span></span>|  
|`false`|<span data-ttu-id="c4617-120">응용 프로그램에서 사용 하는 암호화 알고리즘은 컴퓨터 구성에 관계 없이 FIPS를 준수 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-120">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4617-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c4617-121">Child Elements</span></span>  

 <span data-ttu-id="c4617-122">없음</span><span class="sxs-lookup"><span data-stu-id="c4617-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4617-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c4617-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c4617-124">요소</span><span class="sxs-lookup"><span data-stu-id="c4617-124">Element</span></span>|<span data-ttu-id="c4617-125">설명</span><span class="sxs-lookup"><span data-stu-id="c4617-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c4617-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c4617-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4617-128">설명</span><span class="sxs-lookup"><span data-stu-id="c4617-128">Remarks</span></span>  

 <span data-ttu-id="c4617-129">2.0 .NET Framework부터 암호화 알고리즘을 구현 하는 클래스를 만드는 것은 컴퓨터의 구성에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-129">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="c4617-130">컴퓨터가 FIPS와 호환 되지 않는 알고리즘을 요구 하도록 구성 되어 있고 클래스가 FIPS와 호환 되지 않는 알고리즘을 구현 하는 경우 해당 클래스의 인스턴스를 만들려고 하면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-130">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="c4617-131">생성자는 <xref:System.InvalidOperationException> 예외를 throw 하 고 `Create` 메서드는 <xref:System.Reflection.TargetInvocationException> 내부 예외를 사용 하 여 예외를 throw <xref:System.InvalidOperationException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-131">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="c4617-132">구성에서 fips를 준수 해야 하는 컴퓨터에서 응용 프로그램이 실행 되 고 응용 프로그램에서 FIPS와 호환 되지 않는 알고리즘을 사용 하는 경우 구성 파일에서이 요소를 사용 하 여 CLR (공용 언어 런타임)에서 FIPS 준수를 적용 하지 않도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-132">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="c4617-133">이 요소는 .NET Framework 2.0 서비스 팩 1에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-133">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4617-134">예제</span><span class="sxs-lookup"><span data-stu-id="c4617-134">Example</span></span>  

 <span data-ttu-id="c4617-135">다음 예제에서는 CLR에서 FIPS 준수를 적용 하지 않도록 방지 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4617-135">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4617-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4617-136">See also</span></span>

- [<span data-ttu-id="c4617-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c4617-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c4617-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c4617-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c4617-139">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="c4617-139">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
