---
title: Serialization 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5.0 이상에서 serialization 범주의 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/30/2020
ms.openlocfilehash: f635ff2cd233922a0bbb327de23c8bf25d344fa0
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517413"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="d5db7-103">Serialization 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="d5db7-103">Serialization breaking changes</span></span>

<span data-ttu-id="d5db7-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5db7-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="d5db7-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d5db7-105">Breaking change</span></span> | <span data-ttu-id="d5db7-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d5db7-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="d5db7-107">BinaryFormatter.Deserialize가 SerializationException에서 일부 예외를 다시 래핑</span><span class="sxs-lookup"><span data-stu-id="d5db7-107">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="d5db7-108">5.0</span><span class="sxs-lookup"><span data-stu-id="d5db7-108">5.0</span></span> |

## <a name="net-core-50"></a><span data-ttu-id="d5db7-109">.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="d5db7-109">.NET Core 5.0</span></span>

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
