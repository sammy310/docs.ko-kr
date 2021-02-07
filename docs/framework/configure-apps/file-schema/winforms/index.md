---
description: 자세한 내용은 Windows Forms 구성 섹션을 확인 하세요.
title: Windows Forms 구성 섹션
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: f1eaf2d74c7645d6cf4580d75e23d8910628cce0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697766"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="723c2-103">Windows Forms 구성 섹션</span><span class="sxs-lookup"><span data-stu-id="723c2-103">Windows Forms Configuration Section</span></span>

<span data-ttu-id="723c2-104">Windows Forms 구성 설정을 통해 Windows Forms 앱에서 다중 모니터 지원, 높은 DPI 지원 및 기타 사용자 정의된 구성 설정 등의 사용자 지정된 애플리케이션 설정에 대한 정보를 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723c2-104">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="723c2-105">Windows Forms 애플리케이션 구성 설정은 애플리케이션 구성 파일의 `System.Windows.Forms.ApplicationConfigurationSection` 요소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="723c2-105">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="723c2-106">구문</span><span class="sxs-lookup"><span data-stu-id="723c2-106">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="723c2-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="723c2-107">Attributes and elements</span></span>

<span data-ttu-id="723c2-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="723c2-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="723c2-109">특성</span><span class="sxs-lookup"><span data-stu-id="723c2-109">Attributes</span></span>

<span data-ttu-id="723c2-110">없음</span><span class="sxs-lookup"><span data-stu-id="723c2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="723c2-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="723c2-111">Child elements</span></span>

<span data-ttu-id="723c2-112">요소</span><span class="sxs-lookup"><span data-stu-id="723c2-112">Element</span></span>  |<span data-ttu-id="723c2-113">설명</span><span class="sxs-lookup"><span data-stu-id="723c2-113">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="723c2-114">지정된 된 값과 함께 구성 설정 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="723c2-114">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="723c2-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="723c2-115">Parent elements</span></span>

<span data-ttu-id="723c2-116">요소</span><span class="sxs-lookup"><span data-stu-id="723c2-116">Element</span></span>  |<span data-ttu-id="723c2-117">설명</span><span class="sxs-lookup"><span data-stu-id="723c2-117">Description</span></span> |
---------|---------|
[\<configuration>](../configuration-element.md) | <span data-ttu-id="723c2-118">공용 언어 런타임 및 Windows Forms 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="723c2-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="723c2-119">설명</span><span class="sxs-lookup"><span data-stu-id="723c2-119">Remarks</span></span>

<span data-ttu-id="723c2-120">.NET Framework 4.7부터는 `<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용하여 Windows Forms 애플리케이션을 구성해 최신 .NET Framework 릴리스에 추가된 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723c2-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span>

<span data-ttu-id="723c2-121">`<System.Windows.Forms.ApplicationConfigurationSection>`요소는 [`<add>`](windows-forms-add-configuration-element.md) 각각 특정 구성 설정을 정의 하는 하나 이상의 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723c2-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="723c2-122">참조</span><span class="sxs-lookup"><span data-stu-id="723c2-122">See also</span></span>

- [<span data-ttu-id="723c2-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="723c2-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="723c2-124">Windows Forms의 높은 DPI 지원</span><span class="sxs-lookup"><span data-stu-id="723c2-124">High DPI Support in Windows Forms</span></span>](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
