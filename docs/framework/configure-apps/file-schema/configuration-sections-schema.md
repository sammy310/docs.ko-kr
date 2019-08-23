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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 120733873a7ea29303fe7f82c4c324d411532897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921202"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="818df-102">구성 섹션 스키마</span><span class="sxs-lookup"><span data-stu-id="818df-102">Configuration sections schema</span></span>

<span data-ttu-id="818df-103">구성 섹션 스키마에는 구성 파일의 사용자 지정 설정을 정의 하는 요소가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818df-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="818df-104">구성 파일 및 스키마에 대 한 일반적인 내용은 [.NET Framework 구성 파일 스키마](index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="818df-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

<span data-ttu-id="818df-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="818df-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="818df-106">[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="818df-106">[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="818df-107">[ **\<clear>** ](clear-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="818df-107">[**\<clear>**](clear-element-for-configsections.md) </span></span>  
<span data-ttu-id="818df-108">[ **\<remove>** ](remove-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="818df-108">[**\<remove>**](remove-element-for-configsections.md) </span></span>  
<span data-ttu-id="818df-109">[ **\<section>** ](section-element.md) </span><span class="sxs-lookup"><span data-stu-id="818df-109">[**\<section>**](section-element.md) </span></span>  
[<span data-ttu-id="818df-110"> **\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="818df-110">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="818df-111">Description</span><span class="sxs-lookup"><span data-stu-id="818df-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="818df-112">configsections에 대 한 >를  **\<지웁니다 >**  **\<** </span><span class="sxs-lookup"><span data-stu-id="818df-112">**\<clear>** for **\<configSections>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="818df-113">이전에 정의 된 모든 섹션과 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="818df-113">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="818df-114"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="818df-114">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="818df-115">이전에 정의 된 모든 섹션과 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="818df-115">Clears all previously defined sections and section groups.</span></span> |
| [<span data-ttu-id="818df-116"> **\<configSections>** </span><span class="sxs-lookup"><span data-stu-id="818df-116">**\<configSections>**</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="818df-117">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="818df-117">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="818df-118">configsections에 대 한  **\<> 제거**  **\<>** </span><span class="sxs-lookup"><span data-stu-id="818df-118">**\<remove>** for **\<configSections>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="818df-119">미리 정의 된 섹션 또는 섹션 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="818df-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="818df-120">**configsections \<** 에 대 한 섹션 > > 및  **\<sectionGroup >**  **\<** </span><span class="sxs-lookup"><span data-stu-id="818df-120">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="818df-121">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="818df-121">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="818df-122">configsections에 대 한  **\<sectionGroup >**  **\<>** </span><span class="sxs-lookup"><span data-stu-id="818df-122">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="818df-123">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="818df-123">Defines a namespace for configuration sections.</span></span> |
