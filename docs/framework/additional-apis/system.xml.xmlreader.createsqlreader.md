---
title: XmlReader.CreateSqlReader 방법 (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155741"
---
# <a name="xmlreadercreatesqlreader-method"></a>XmlReader.CreateSqlReader 메서드

구문 분석을 위해 지정한 스트림, 설정 및 컨텍스트 정보를 사용하여 새 <xref:System.Xml.XmlReader> 인스턴스를 만듭니다.

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a>매개 변수

- `input` <xref:System.IO.Stream>  
  XML 데이터가 포함된 스트림입니다.

- `settings` <xref:System.Xml.XmlReaderSettings>  
  새 <xref:System.Xml.XmlReader> 인스턴스의 설정입니다. 이 값은 `null`일 수 있습니다.

- `inputContext` <xref:System.Xml.XmlParserContext>  
  XML 조각을 구문 분석하는 데 필요한 컨텍스트 정보입니다. 이 값은 `null`일 수 있습니다.

## <a name="returns"></a>반환

<xref:System.Xml.XmlReader>  
스트림의 XML 데이터를 읽는 데 사용되는 개체입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> 메서드는 `XmlReader.CreateSqlReader` 내부이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 메서드의 사용을 지원하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:**<xref:System.Xml>

**어셈블리:** 시스템.Xml.dll

**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.
