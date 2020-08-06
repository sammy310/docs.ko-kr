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
# <a name="serialization-breaking-changes"></a>Serialization 관련 호환성이 손상되는 변경

이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.

| 주요 변경 내용 | 도입된 버전 |
| - | - |
| [BinaryFormatter.Deserialize가 SerializationException에서 일부 예외를 다시 래핑](#binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception) | 5.0 |

## <a name="net-core-50"></a>.NET Core 5.0

[!INCLUDE [binaryformatter-deserialize-rewraps-exceptions](../../../includes/core-changes/serialization/5.0/binaryformatter-deserialize-rewraps-exceptions.md)]

***
