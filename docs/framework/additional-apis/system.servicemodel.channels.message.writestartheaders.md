---
title: WriteStartHeaders 메서드 (System.servicemodel)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: a2c82ee4029c7af0396219f5ded8c999fd01d65b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451289"
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

**네임스페이스:** <xref:System.ServiceModel.Channels>

**어셈블리:** System.servicemodel

**.NET Framework 버전:** 3.0부터 사용할 수 있습니다.
