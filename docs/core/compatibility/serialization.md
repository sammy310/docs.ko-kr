---
title: Serialization 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5.0 이상에서 serialization 범주의 호환성이 손상되는 변경을 나열합니다.
ms.date: 07/30/2020
ms.openlocfilehash: 67608c8e7a9745c060b7eb179fe5a956ede9f80f
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332884"
---
# <a name="serialization-breaking-changes"></a><span data-ttu-id="fa109-103">Serialization 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="fa109-103">Serialization breaking changes</span></span>

<span data-ttu-id="fa109-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa109-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="fa109-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="fa109-105">Breaking change</span></span> | <span data-ttu-id="fa109-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="fa109-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="fa109-107">ASP.NET Core 앱은 따옴표 붙은 숫자를 역직렬화할 수 있음</span><span class="sxs-lookup"><span data-stu-id="fa109-107">ASP.NET Core apps allow deserializing quoted numbers</span></span>](#aspnet-core-apps-allow-deserializing-quoted-numbers) | <span data-ttu-id="fa109-108">5.0</span><span class="sxs-lookup"><span data-stu-id="fa109-108">5.0</span></span> |
| [<span data-ttu-id="fa109-109">PropertyNamingPolicy, PropertyNameCaseInsensitive 및 Encoder 옵션은 키-값 쌍을 직렬화 및 역직렬화할 때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa109-109">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | <span data-ttu-id="fa109-110">5.0</span><span class="sxs-lookup"><span data-stu-id="fa109-110">5.0</span></span> |
| [<span data-ttu-id="fa109-111">역직렬화에 사용되지 않는 비공용 매개 변수가 없는 생성자</span><span class="sxs-lookup"><span data-stu-id="fa109-111">Non-public, parameterless constructors not used for deserialization</span></span>](#non-public-parameterless-constructors-not-used-for-deserialization) | <span data-ttu-id="fa109-112">5.0</span><span class="sxs-lookup"><span data-stu-id="fa109-112">5.0</span></span> |
| [<span data-ttu-id="fa109-113">형식 매개 변수가 null인 경우 JsonSerializer.Serialize에서 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="fa109-113">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | <span data-ttu-id="fa109-114">5.0</span><span class="sxs-lookup"><span data-stu-id="fa109-114">5.0</span></span> |
| [<span data-ttu-id="fa109-115">JsonSerializer.Deserialize에는 단일 문자열이 필요함</span><span class="sxs-lookup"><span data-stu-id="fa109-115">JsonSerializer.Deserialize requires single-character string</span></span>](#jsonserializerdeserialize-requires-single-character-string) | <span data-ttu-id="fa109-116">5.0</span><span class="sxs-lookup"><span data-stu-id="fa109-116">5.0</span></span> |
| [<span data-ttu-id="fa109-117">BinaryFormatter.Deserialize가 SerializationException에서 일부 예외를 다시 래핑</span><span class="sxs-lookup"><span data-stu-id="fa109-117">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | <span data-ttu-id="fa109-118">5.0</span><span class="sxs-lookup"><span data-stu-id="fa109-118">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="fa109-119">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="fa109-119">.NET 5.0</span></span>

[!INCLUDE [jsonserializer-allows-reading-numbers-as-strings](../../../includes/core-changes/serialization/5.0/jsonserializer-allows-reading-numbers-as-strings.md)]

***

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

<span data-ttu-id="fa109-120">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fa109-120">\*\*_</span></span>

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

_*_

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

_*_

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

_*_

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

<span data-ttu-id="fa109-121">_\*\*</span><span class="sxs-lookup"><span data-stu-id="fa109-121">_\*\*</span></span>
