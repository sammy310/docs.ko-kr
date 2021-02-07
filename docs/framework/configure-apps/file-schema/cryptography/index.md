---
description: '자세한 정보: 암호화 설정 스키마'
title: 암호화 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: a7b3c020ed760aba24c9faf020281b7ad4bf3af7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730085"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="b5387-103">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b5387-103">Cryptography Settings Schema</span></span>

<span data-ttu-id="b5387-104">암호 설정 스키마에는 암호화 알고리즘을 구현하는 클래스에 알고리즘 이름을 매핑하는 방법을 지정하는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-104">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)

|<span data-ttu-id="b5387-105">요소</span><span class="sxs-lookup"><span data-stu-id="b5387-105">Element</span></span>|<span data-ttu-id="b5387-106">설명</span><span class="sxs-lookup"><span data-stu-id="b5387-106">Description</span></span>|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](cryptoclasses-element.md)|<span data-ttu-id="b5387-107">요소의 이름에 매핑되는 암호화 클래스의 목록을 포함 **\<nameEntry>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-107">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptoClass**>](cryptoclass-element.md)|<span data-ttu-id="b5387-108">요소의 이름에 매핑되는 암호화 클래스를 포함 **\<nameEntry>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-108">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[**\<cryptographySettings**>](cryptographysettings-element.md)|<span data-ttu-id="b5387-109">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-109">Contains cryptography settings.</span></span>|  
|[**\<cryptoNameMapping**>](cryptonamemapping-element.md)|<span data-ttu-id="b5387-110">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-110">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="b5387-111">**\<mscorlib>** 암호화 설정에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="b5387-111">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="b5387-112">요소를 포함 **\<cryptographySettings>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-112">Contains the **\<cryptographySettings>** element.</span></span>|  
|[**\<nameEntry>**](nameentry-element.md)|<span data-ttu-id="b5387-113">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[**\<oidEntry>**](oidentry-element.md)|<span data-ttu-id="b5387-114">ASN.1 OID(개체 식별자)를 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-114">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[**\<oidMap>**](oidmap-element.md)|<span data-ttu-id="b5387-115">클래스에 대한 ASN.1 OID 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5387-115">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5387-116">참조</span><span class="sxs-lookup"><span data-stu-id="b5387-116">See also</span></span>

- [<span data-ttu-id="b5387-117">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b5387-117">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b5387-118">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="b5387-118">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
