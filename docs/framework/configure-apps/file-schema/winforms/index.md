---
title: Windows Forms 구성 섹션
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e76e11ef8bb39d72cb16655c948354bc326e75bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913092"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="9f8e0-102">Windows Forms 구성 섹션</span><span class="sxs-lookup"><span data-stu-id="9f8e0-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="9f8e0-103">Windows Forms 구성 설정을 통해 Windows Forms 앱에서 다중 모니터 지원, 높은 DPI 지원 및 기타 사용자 정의된 구성 설정 등의 사용자 지정된 애플리케이션 설정에 대한 정보를 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e0-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="9f8e0-104">Windows Forms 애플리케이션 구성 설정은 애플리케이션 구성 파일의 `System.Windows.Forms.ApplicationConfigurationSection` 요소에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e0-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f8e0-105">구문</span><span class="sxs-lookup"><span data-stu-id="9f8e0-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f8e0-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9f8e0-106">Attributes and elements</span></span>

<span data-ttu-id="9f8e0-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f8e0-108">특성</span><span class="sxs-lookup"><span data-stu-id="9f8e0-108">Attributes</span></span>

<span data-ttu-id="9f8e0-109">없음</span><span class="sxs-lookup"><span data-stu-id="9f8e0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f8e0-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9f8e0-110">Child elements</span></span>

<span data-ttu-id="9f8e0-111">요소</span><span class="sxs-lookup"><span data-stu-id="9f8e0-111">Element</span></span>  |<span data-ttu-id="9f8e0-112">설명</span><span class="sxs-lookup"><span data-stu-id="9f8e0-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="9f8e0-113">지정된 된 값과 함께 구성 설정 키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e0-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="9f8e0-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9f8e0-114">Parent elements</span></span>

<span data-ttu-id="9f8e0-115">요소</span><span class="sxs-lookup"><span data-stu-id="9f8e0-115">Element</span></span>  |<span data-ttu-id="9f8e0-116">설명</span><span class="sxs-lookup"><span data-stu-id="9f8e0-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="9f8e0-117">\<구성></span><span class="sxs-lookup"><span data-stu-id="9f8e0-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="9f8e0-118">공용 언어 런타임 및 Windows Forms 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e0-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="9f8e0-119">설명</span><span class="sxs-lookup"><span data-stu-id="9f8e0-119">Remarks</span></span>

<span data-ttu-id="9f8e0-120">.NET Framework 4.7부터는 `<System.Windows.Forms.ApplicationConfigurationSection>` 요소를 사용하여 Windows Forms 애플리케이션을 구성해 최신 .NET Framework 릴리스에 추가된 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e0-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="9f8e0-121">`<System.Windows.Forms.ApplicationConfigurationSection>` 요소는 각각 특정 구성 설정을 정의하는 하나 이상의 [`<add>`](windows-forms-add-configuration-element.md) 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e0-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f8e0-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f8e0-122">See also</span></span>

- [<span data-ttu-id="9f8e0-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9f8e0-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9f8e0-124">Windows Forms의 높은 DPI 지원</span><span class="sxs-lookup"><span data-stu-id="9f8e0-124">High DPI Support in Windows Forms</span></span>](../../../winforms/high-dpi-support-in-windows-forms.md)
