---
title: WriteStartHeaders 메서드 (System.servicemodel)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214872"
---
# <a name="messagewritestartheaders-method"></a>WriteStartHeaders 메서드

<xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> 메서드를 호출 하 여 시작 헤더를 XML 파일에 씁니다.

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a>매개 변수

- `writer` <xref:System.Xml.XmlDictionaryWriter>\
  시작 헤더를 XML 파일에 쓰는 데 사용 되는 작성기입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `Message.WriteStartHeaders` 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임 스페이스:** <xref:System.ServiceModel.Channels>

**어셈블리:** System.servicemodel

**.NET Framework 버전:** 3.0부터 사용할 수 있습니다.
