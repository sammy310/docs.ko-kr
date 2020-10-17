---
title: Serialization 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5.0 이상에서 serialization 범주의 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/30/2020
ms.openlocfilehash: 65006e6fb45ed2d54699c9972e0489e3ac5ac8bc
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955340"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="8cf0a-103">Serialization 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="8cf0a-103">Serialization breaking changes</span></span>

<span data-ttu-id="8cf0a-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf0a-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="8cf0a-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="8cf0a-105">Breaking change</span></span> | <span data-ttu-id="8cf0a-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="8cf0a-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="8cf0a-107">형식 매개 변수가 null인 경우 JsonSerializer.Serialize에서 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="8cf0a-107">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="8cf0a-108">5.0</span><span class="sxs-lookup"><span data-stu-id="8cf0a-108">5.0</span></span> |
| [<span data-ttu-id="8cf0a-109">JsonSerializer.Deserialize에는 단일 문자열이 필요함</span><span class="sxs-lookup"><span data-stu-id="8cf0a-109">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="8cf0a-110">5.0</span><span class="sxs-lookup"><span data-stu-id="8cf0a-110">5.0</span></span> |
| [<span data-ttu-id="8cf0a-111">BinaryFormatter.Deserialize가 SerializationException에서 일부 예외를 다시 래핑</span><span class="sxs-lookup"><span data-stu-id="8cf0a-111">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="8cf0a-112">5.0</span><span class="sxs-lookup"><span data-stu-id="8cf0a-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="8cf0a-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="8cf0a-113">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

***

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

***

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
