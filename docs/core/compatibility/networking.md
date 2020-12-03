---
title: 네트워킹 관련 호환성이 손상되는 변경
description: .NET Core 2.0 및 3.0의 네트워킹 관련 호환성이 손상되는 변경을 나열합니다.
ms.date: 05/05/2020
ms.openlocfilehash: 761c6481888bcb8e91f7b4212355aca067632495
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689214"
---
# <a name="networking-breaking-changes-in-net-core-20-and-30"></a><span data-ttu-id="75900-103">.NET Core 2.0 및 3.0의 네트워킹 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="75900-103">Networking breaking changes in .NET Core 2.0 and 3.0</span></span>

<span data-ttu-id="75900-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75900-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="75900-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="75900-105">Breaking change</span></span> | <span data-ttu-id="75900-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="75900-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="75900-107">HttpRequestMessage.Version의 기본값은 1.1로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75900-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="75900-108">3.0</span><span class="sxs-lookup"><span data-stu-id="75900-108">3.0</span></span> |
| [<span data-ttu-id="75900-109">WebClient.CancelAsync가 항상 즉시 취소되지는 않음</span><span class="sxs-lookup"><span data-stu-id="75900-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="75900-110">2.0</span><span class="sxs-lookup"><span data-stu-id="75900-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="75900-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="75900-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="75900-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="75900-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***
