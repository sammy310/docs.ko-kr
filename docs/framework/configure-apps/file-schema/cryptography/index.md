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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088000"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="3349b-102">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3349b-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="3349b-103">암호 설정 스키마에는 암호화 알고리즘을 구현하는 클래스에 알고리즘 이름을 매핑하는 방법을 지정하는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
<span data-ttu-id="3349b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3349b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3349b-105">[**mscorlib >\<** ](mscorlib-element-for-cryptography-settings.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="3349b-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="3349b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptographySettings**](cryptographysettings-element.md) ></span><span class="sxs-lookup"><span data-stu-id="3349b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\</span></span>
<span data-ttu-id="3349b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="3349b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="3349b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**cryptoClasses\<** ](cryptoclasses-element.md) ></span><span class="sxs-lookup"><span data-stu-id="3349b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\</span></span>
<span data-ttu-id="3349b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**cryptoClass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="3349b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>\
<span data-ttu-id="3349b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<nameEntry**](nameentry-element.md) ></span><span class="sxs-lookup"><span data-stu-id="3349b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)\</span></span>
<span data-ttu-id="3349b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="3349b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="3349b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<y >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="3349b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>

|<span data-ttu-id="3349b-113">요소</span><span class="sxs-lookup"><span data-stu-id="3349b-113">Element</span></span>|<span data-ttu-id="3349b-114">설명</span><span class="sxs-lookup"><span data-stu-id="3349b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3349b-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="3349b-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="3349b-116">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="3349b-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="3349b-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="3349b-118">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="3349b-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="3349b-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="3349b-120">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="3349b-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="3349b-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="3349b-122">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="3349b-123">암호화 설정에 대한 **\<mscorlib>** 요소</span><span class="sxs-lookup"><span data-stu-id="3349b-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="3349b-124">**\<cryptographySettings>** 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="3349b-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="3349b-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="3349b-126">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="3349b-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="3349b-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="3349b-128">ASN.1 OID(개체 식별자)를 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="3349b-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="3349b-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="3349b-130">클래스에 대한 ASN.1 OID 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3349b-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3349b-131">참조</span><span class="sxs-lookup"><span data-stu-id="3349b-131">See also</span></span>

- [<span data-ttu-id="3349b-132">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3349b-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3349b-133">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="3349b-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
