---
title: <xmlSerializer> 요소
description: <xmlSerializer> 요소는 XmlSerializer의 진행에 대한 추가 검사가 수행되는지 여부를 지정합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 6f368880c97a21dc3e9593ecb2319d265a1b8932
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676493"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="ae74c-103">\<xmlSerializer> 요소</span><span class="sxs-lookup"><span data-stu-id="ae74c-103">\<xmlSerializer> Element</span></span>

<span data-ttu-id="ae74c-104"><xref:System.Xml.Serialization.XmlSerializer>의 진행에 대한 추가 검사가 수행되었는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a><span data-ttu-id="ae74c-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae74c-105">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae74c-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ae74c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ae74c-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae74c-108">특성</span><span class="sxs-lookup"><span data-stu-id="ae74c-108">Attributes</span></span>  
  
|<span data-ttu-id="ae74c-109">특성</span><span class="sxs-lookup"><span data-stu-id="ae74c-109">Attribute</span></span>|<span data-ttu-id="ae74c-110">설명</span><span class="sxs-lookup"><span data-stu-id="ae74c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae74c-111">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="ae74c-111">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="ae74c-112"><xref:System.Xml.Serialization.XmlSerializer>의 진행률이 검사되었는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-112">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="ae74c-113">특성을 "true" 또는 "false"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-113">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="ae74c-114">기본값은 "true"입니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-114">The default is "true".</span></span>|  
|<span data-ttu-id="ae74c-115">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="ae74c-115">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="ae74c-116"><xref:System.Xml.Serialization.XmlSerializer>가 C# 코드를 파일에 쓴 다음 어셈블리로 컴파일하여 어셈블리를 생성하는 레거시 serialization 생성을 사용하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-116">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="ae74c-117">기본값은 **false** 입니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-117">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae74c-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ae74c-118">Child Elements</span></span>  

 <span data-ttu-id="ae74c-119">없음</span><span class="sxs-lookup"><span data-stu-id="ae74c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae74c-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ae74c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ae74c-121">요소</span><span class="sxs-lookup"><span data-stu-id="ae74c-121">Element</span></span>|<span data-ttu-id="ae74c-122">설명</span><span class="sxs-lookup"><span data-stu-id="ae74c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae74c-123">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="ae74c-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="ae74c-124"><xref:System.Xml.Serialization.XmlSerializer> 및 <xref:System.Xml.Serialization.XmlSchemaImporter> 클래스에 대한 구성 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-124">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae74c-125">설명</span><span class="sxs-lookup"><span data-stu-id="ae74c-125">Remarks</span></span>  

 <span data-ttu-id="ae74c-126">기본적으로 <xref:System.Xml.Serialization.XmlSerializer>는 신뢰할 수 없는 데이터를 역직렬화할 때 잠재적 서비스 거부 공격에 대한 추가 보안 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-126">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="ae74c-127">deserialization 도중 무한 루프의 탐지를 시도하여 이러한 보안을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-127">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="ae74c-128">이러한 조건이 검색되면 다음과 같은 메시지와 함께 예외가 throw됩니다. "내부 오류: 기본 스트림에 대한 deserialization을 계속할 수 없습니다."</span><span class="sxs-lookup"><span data-stu-id="ae74c-128">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="ae74c-129">이 메시지가 반드시 서비스 거부 공격이 진행 중임을 의미하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-129">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="ae74c-130">드문 경우지만 무한 루프 검색 메커니즘이 가양성(false positive)을 생성하여 적법한 들어오는 메시지에 대해 예외가 throw될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-130">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="ae74c-131">특정 애플리케이션에서 적법한 메시지가 이러한 추가 보호 계층에 의해 거부된 경우 **checkDeserializeAdvances** 특성을 “false”로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-131">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae74c-132">예제</span><span class="sxs-lookup"><span data-stu-id="ae74c-132">Example</span></span>  

 <span data-ttu-id="ae74c-133">다음 코드 예제에서는 **checkDeserializeAdvances** 특성을 “false”로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae74c-133">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae74c-134">참조</span><span class="sxs-lookup"><span data-stu-id="ae74c-134">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="ae74c-135">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="ae74c-135">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="ae74c-136">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="ae74c-136">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
