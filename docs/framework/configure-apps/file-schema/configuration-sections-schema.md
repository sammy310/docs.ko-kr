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
ms.openlocfilehash: fc43a9c32ba33629b6e89120cf57f6d212ab3a56
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441663"
---
# <a name="configuration-sections-schema"></a><span data-ttu-id="4147a-102">구성 섹션 스키마</span><span class="sxs-lookup"><span data-stu-id="4147a-102">Configuration sections schema</span></span>

<span data-ttu-id="4147a-103">구성 섹션 스키마에는 구성 파일의 사용자 지정 설정을 정의 하는 요소가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4147a-103">The configuration sections schema contains elements that define custom settings in configuration files.</span></span> <span data-ttu-id="4147a-104">구성 파일 및 스키마에 대 한 일반적인 내용은 [.NET Framework 구성 파일 스키마](index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4147a-104">For general information on configuration files and schemas, see [Configuration file schema for the .NET Framework](index.md).</span></span>

[**\<configuration>**](configuration-element.md)
[**\<configSections>**](configsections-element-for-configuration.md)
[**\<section>**](section-element.md)
[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)

|     | <span data-ttu-id="4147a-105">설명</span><span class="sxs-lookup"><span data-stu-id="4147a-105">Description</span></span> |
| --- | ----------- |
| [**\<configSections>**](configsections-element-for-configuration.md) | <span data-ttu-id="4147a-106">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4147a-106">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="4147a-107">**\<section>** 및의 경우 **\<configSections>\*\*\*\*\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="4147a-107">**\<section>** for **\<configSections>** and **\<sectionGroup>**</span></span>](section-element.md) | <span data-ttu-id="4147a-108">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4147a-108">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="4147a-109">**\<sectionGroup>** 에 대 한**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="4147a-109">**\<sectionGroup>** for **\<configSections>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="4147a-110">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4147a-110">Defines a namespace for configuration sections.</span></span> |

<a name="dep"></a>

## <a name="unimplemented-elements"></a><span data-ttu-id="4147a-111">구현 되지 않은 요소</span><span class="sxs-lookup"><span data-stu-id="4147a-111">Unimplemented elements</span></span>

<span data-ttu-id="4147a-112">다음 요소는 영향을 주지 않으며 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4147a-112">The following elements have no impact and should not be used:</span></span>

* **\<clear>**
* **\<remove>**
