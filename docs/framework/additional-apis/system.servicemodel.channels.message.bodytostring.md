---
description: '자세히 알아보기: BodyToString 메서드'
title: BodyToString 메서드 (System.servicemodel)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: babcd881d191ff46b98e9999c4ff04166479a68d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699378"
---
# <a name="messagebodytostring-method"></a>BodyToString 메서드

메서드를 호출 하 여 메시지 본문을 문자열로 변환 합니다 <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> .

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a>매개 변수

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  메시지 본문을 문자열로 변환 하는 데 사용 되는 작성기입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `Message.BodyToString`메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.ServiceModel.Channels>

**어셈블리:** System.ServiceModel.dll

**.NET Framework 버전:** 3.0부터 사용할 수 있습니다.
