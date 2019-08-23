---
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
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927625"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="5caa3-102">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5caa3-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="5caa3-103">암호 설정 스키마에는 암호화 알고리즘을 구현하는 클래스에 알고리즘 이름을 매핑하는 방법을 지정하는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="5caa3-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="5caa3-105"> **\<mscorlib>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="5caa3-106"> **\<cryptographySettings>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="5caa3-107"> **\<cryptoNameMapping>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="5caa3-108"> **\<cryptoClasses>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="5caa3-109"> **\<cryptoClass>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="5caa3-110"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="5caa3-111"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="5caa3-112"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="5caa3-113">요소</span><span class="sxs-lookup"><span data-stu-id="5caa3-113">Element</span></span>|<span data-ttu-id="5caa3-114">Description</span><span class="sxs-lookup"><span data-stu-id="5caa3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5caa3-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="5caa3-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="5caa3-116">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="5caa3-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="5caa3-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="5caa3-118">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="5caa3-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="5caa3-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="5caa3-120">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="5caa3-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="5caa3-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="5caa3-122">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="5caa3-123">암호화 설정에 대한 **\<mscorlib>** 요소</span><span class="sxs-lookup"><span data-stu-id="5caa3-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="5caa3-124">**\<cryptographySettings>** 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="5caa3-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="5caa3-126">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="5caa3-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="5caa3-128">ASN.1 OID(개체 식별자)를 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="5caa3-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="5caa3-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="5caa3-130">클래스에 대한 ASN.1 OID 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5caa3-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5caa3-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="5caa3-131">See also</span></span>

- [<span data-ttu-id="5caa3-132">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="5caa3-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5caa3-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="5caa3-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
