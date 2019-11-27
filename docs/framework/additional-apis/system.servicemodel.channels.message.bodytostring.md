---
title: BodyToString 메서드 (System.servicemodel)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 7b0b56bfda1c0c37f43f95e9684d3b4042c1b97c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451313"
---
# <a name="messagebodytostring-method"></a>BodyToString 메서드

<xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> 메서드를 호출 하 여 메시지 본문을 문자열로 변환 합니다.

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>매개 변수

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  메시지 본문을 문자열로 변환 하는 데 사용 되는 작성기입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `Message.BodyToString` 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.ServiceModel.Channels>

**어셈블리:** System.servicemodel

**.NET Framework 버전:** 3.0부터 사용할 수 있습니다.
