---
title: <cryptographySettings> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: 3c3513c05485550202f2fc5bcae1faabb0e75d47
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201813"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="4540f-102">\<cryptographySettings> 요소</span><span class="sxs-lookup"><span data-stu-id="4540f-102">\<cryptographySettings> Element</span></span>

<span data-ttu-id="4540f-103">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-103">Contains cryptography settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**

## <a name="syntax"></a><span data-ttu-id="4540f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4540f-104">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4540f-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4540f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4540f-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4540f-107">특성</span><span class="sxs-lookup"><span data-stu-id="4540f-107">Attributes</span></span>  

 <span data-ttu-id="4540f-108">없음</span><span class="sxs-lookup"><span data-stu-id="4540f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4540f-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4540f-109">Child Elements</span></span>  
  
|<span data-ttu-id="4540f-110">요소</span><span class="sxs-lookup"><span data-stu-id="4540f-110">Element</span></span>|<span data-ttu-id="4540f-111">설명</span><span class="sxs-lookup"><span data-stu-id="4540f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](cryptonamemapping-element.md)|<span data-ttu-id="4540f-112">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-112">Contains mappings of classes to friendly names.</span></span>|  
|[\<oidMap>](oidmap-element.md)|<span data-ttu-id="4540f-113">클래스에 대 한 OID (개체 식별자) 매핑을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-113">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4540f-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4540f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4540f-115">요소</span><span class="sxs-lookup"><span data-stu-id="4540f-115">Element</span></span>|<span data-ttu-id="4540f-116">설명</span><span class="sxs-lookup"><span data-stu-id="4540f-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4540f-117">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="4540f-118">요소를 포함 `cryptographySettings` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4540f-119">예제</span><span class="sxs-lookup"><span data-stu-id="4540f-119">Example</span></span>  

 <span data-ttu-id="4540f-120">다음 예제에서는 요소를 사용 하 여 **\<cryptographySettings>** 암호화 이름 매핑과 OID 매핑을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-120">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="4540f-121">이 예제에서는가 <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> 개체를 반환 하 `MyHashClass` 고 `MyCryptoClass` 클래스가 개체 식별자 1.3.36.2.1에 매핑되도록 런타임을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4540f-121">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4540f-122">참조</span><span class="sxs-lookup"><span data-stu-id="4540f-122">See also</span></span>

- [<span data-ttu-id="4540f-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="4540f-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4540f-124">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4540f-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4540f-125">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="4540f-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
