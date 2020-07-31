---
title: '완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현'
description: .NET Framework 4.6.1 이상 버전을 대상으로 하는 Windows Forms 앱에 포함된 사용자 지정 IMessageFilter.PreFilterMessage 구현에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5fe7500d3ed6ff293514495df150a747e7946dda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475257"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="9a799-103">완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현</span><span class="sxs-lookup"><span data-stu-id="9a799-103">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="9a799-104">.NET Framework 4.6.1부터 .NET Framework 버전을 대상으로 하는 Windows Forms 앱에서는 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 다음에 해당하는 경우 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드를 호출할 때 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 메시지를 안전하게 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a799-104">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="9a799-105">다음 중 하나 또는 두 가지 모두를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a799-105">Does one or both of the following:</span></span>

  - <span data-ttu-id="9a799-106"><xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드를 호출하여 메시지 필터 추가</span><span class="sxs-lookup"><span data-stu-id="9a799-106">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="9a799-107"><xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 메서드를 호출하여 메시지 필터 제거</span><span class="sxs-lookup"><span data-stu-id="9a799-107">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="9a799-108">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9a799-108">method.</span></span>

- <span data-ttu-id="9a799-109">**그와 동시에**<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 메서드를 호출하여 메시지를 펌핑하는 경우</span><span class="sxs-lookup"><span data-stu-id="9a799-109">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="9a799-110">영향</span><span class="sxs-lookup"><span data-stu-id="9a799-110">Impact</span></span>

<span data-ttu-id="9a799-111">이 변경은 .NET Framework 4.6.1부터 .NET Framework 버전을 대상으로 하는 Windows Forms 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a799-111">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="9a799-112">이전 버전의 .NET Framework를 대상으로 하는 Windows Forms 앱에서는 경우에 따라 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드를 호출할 때 이러한 구현이 <xref:System.IndexOutOfRangeException> 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a799-112">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="9a799-113">완화</span><span class="sxs-lookup"><span data-stu-id="9a799-113">Mitigation</span></span>

<span data-ttu-id="9a799-114">이러한 변경을 원치 않는 경우 .NET Framework 4.6.1 이상 버전을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a799-114">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="9a799-115">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.1 이상 버전에서 실행되는 앱은 앱 구성 파일의 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a799-115">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="9a799-116">참조</span><span class="sxs-lookup"><span data-stu-id="9a799-116">See also</span></span>

- [<span data-ttu-id="9a799-117">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="9a799-117">Application compatibility</span></span>](application-compatibility.md)
