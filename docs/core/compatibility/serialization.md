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
# <a name="serialization-breaking-changes"></a>Serialization 관련 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | - |
| [ASP.NET Core 앱은 따옴표 붙은 숫자를 역직렬화할 수 있음](#aspnet-core-apps-allow-deserializing-quoted-numbers) | 5.0 |
| [PropertyNamingPolicy, PropertyNameCaseInsensitive 및 Encoder 옵션은 키-값 쌍을 직렬화 및 역직렬화할 때 적용됩니다.](#propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs) | 5.0 |
| [역직렬화에 사용되지 않는 비공용 매개 변수가 없는 생성자](#non-public-parameterless-constructors-not-used-for-deserialization) | 5.0 |
| [형식 매개 변수가 null인 경우 JsonSerializer.Serialize에서 ArgumentNullException을 throw함](#jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null) | 5.0 |
| [JsonSerializer.Deserialize에는 단일 문자열이 필요함](#jsonserializerdeserialize-requires-single-character-string) | 5.0 |
| [BinaryFormatter.Deserialize가 SerializationException에서 일부 예외를 다시 래핑](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [jsonserializer-allows-reading-numbers-as-strings](../../../includes/core-changes/serialization/5.0/jsonserializer-allows-reading-numbers-as-strings.md)]

***

[!INCLUDE [options-honored-when-serializing-key-value-pairs](../../../includes/core-changes/serialization/5.0/options-honored-when-serializing-key-value-pairs.md)]

**_

[!INCLUDE [non-public-parameterless-constructors-not-used-for-deserialization](../../../includes/core-changes/serialization/5.0/non-public-parameterless-constructors-not-used-for-deserialization.md)]

_*_

[!INCLUDE [jsonserializer-serialize-throws-argumentnullexception-for-null-type](../../../includes/core-changes/serialization/5.0/jsonserializer-serialize-throws-argumentnullexception-for-null-type.md)]

_*_

[!INCLUDE [deserializing-json-into-char-requires-single-character](../../../includes/core-changes/serialization/5.0/deserializing-json-into-char-requires-single-character.md)]

_*_

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

_**
