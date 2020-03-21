---
title: 구성 섹션 스키마
ms.date: 05/02/2017
helpviewer_keywords:
- configuration settings [.NET Framework], custom
- schema configuration settings
- configuration sections [.NET Framework]
- custom elements
- configuration schema [.NET Framework], custom settings in configuration files
- elements [.NET Framework], custom settings in configuration files
ms.assetid: 6e4cc793-c526-4007-b4e9-37d56295f2cb
ms.openlocfilehash: 28f936e6fd7c9e7f6f895396df8e8b8d36ab9139
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155325"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="ee19a-102">구성 섹션 스키마</span><span class="sxs-lookup"><span data-stu-id="ee19a-102">Configuration sections schema</span></span>

<span data-ttu-id="ee19a-103">구성 섹션 스키마에는 구성 파일의 사용자 지정 설정을 정의하는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee19a-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="ee19a-104">구성 파일 및 스키마에 대한 일반적인 정보는 [.NET Framework에 대한 구성 파일 스키마](index.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee19a-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="ee19a-105">[**\<구성>** ](configuration-element.md) 
 [\*\* \< \*\*](section-element.md) 
 
 
 
 [\*\* \< \*\*](remove-element-for-configsections.md) [\*\* \< \*\*](clear-element-for-configsections.md) [**구성섹션섹션>>\<**](sectiongroup-element-for-configsections.md) 섹션>제거>지우기>>>[\*\* \< \*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="ee19a-105">[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<clear>**](clear-element-for-configsections.md)
[**\<remove>**](remove-element-for-configsections.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>

|     | <span data-ttu-id="ee19a-106">Description</span><span class="sxs-lookup"><span data-stu-id="ee19a-106">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ee19a-107">>구성섹션에 대한 \*\* \<\*\* \*\* \<명확한>\*\*</span><span class="sxs-lookup"><span data-stu-id="ee19a-107">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="ee19a-108">이전에 정의된 모든 단면 및 단면 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ee19a-108">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="ee19a-109">**\<클리어>**</span><span class="sxs-lookup"><span data-stu-id="ee19a-109">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="ee19a-110">이전에 정의된 모든 단면 및 단면 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ee19a-110">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="ee19a-111">**\<>섹션**</span><span class="sxs-lookup"><span data-stu-id="ee19a-111">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="ee19a-112">구성 섹션 및 네임스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ee19a-112">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="ee19a-113">구성 섹션>대한 \*\* \<\*\* \*\* \<>제거\*\*</span><span class="sxs-lookup"><span data-stu-id="ee19a-113">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="ee19a-114">미리 정의된 단면 또는 단면 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ee19a-114">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="ee19a-115">구성섹션 \*\* \<>\*\* 및 \*\* \<섹션그룹>\*\* 대한 섹션>\*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="ee19a-115">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="ee19a-116">구성 섹션 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ee19a-116">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="ee19a-117">구성 섹션>대한 \*\* \<\*\* \*\* \<섹션 그룹>\*\*</span><span class="sxs-lookup"><span data-stu-id="ee19a-117">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="ee19a-118">구성 섹션에 대한 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ee19a-118">Defines a namespace for configuration sections.</span></span> |
