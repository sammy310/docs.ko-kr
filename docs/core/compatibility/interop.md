---
title: Interop 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5.0 이상에서 interop 관련 호환성이 손상되는 변경 내용을 나열합니다.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438033"
---
# <a name="interop-breaking-changes"></a><span data-ttu-id="18b6c-103">Interop 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="18b6c-103">Interop breaking changes</span></span>

<span data-ttu-id="18b6c-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18b6c-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="18b6c-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="18b6c-105">Breaking change</span></span> | <span data-ttu-id="18b6c-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="18b6c-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="18b6c-107">RCW를 `InterfaceIsIInspectable` 인터페이스로 캐스팅하면 PlatformNotSupportedException이 throw됨</span><span class="sxs-lookup"><span data-stu-id="18b6c-107">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | <span data-ttu-id="18b6c-108">5.0</span><span class="sxs-lookup"><span data-stu-id="18b6c-108">5.0</span></span> |
| [<span data-ttu-id="18b6c-109">비 Windows 플랫폼에서 A/W 접미사 검색 안 함</span><span class="sxs-lookup"><span data-stu-id="18b6c-109">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="18b6c-110">5.0</span><span class="sxs-lookup"><span data-stu-id="18b6c-110">5.0</span></span> |
| [<span data-ttu-id="18b6c-111">WinRT의 기본 제공 지원이 .NET에서 제거됨</span><span class="sxs-lookup"><span data-stu-id="18b6c-111">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="18b6c-112">5.0</span><span class="sxs-lookup"><span data-stu-id="18b6c-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="18b6c-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="18b6c-113">.NET 5.0</span></span>

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
