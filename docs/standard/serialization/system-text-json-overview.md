---
title: C#을 사용하여 JSON 직렬화 및 역직렬화 - .NET
description: 이 개요에서는 .NET에서 JSON으로 직렬화 및 역직렬화하는 System.Text.Json 네임스페이스 기능에 대해 설명합니다.
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: cb5c15c2a5c336e2d5b4a3754fa7a02a370602f3
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009887"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>.NET의 JSON 직렬화 및 역직렬화(마샬링 및 역 마샬링) - 개요

`System.Text.Json` 네임스페이스는 JSON(JavaScript Object Notation)에서 직렬화 및 역직렬화하는 기능을 제공합니다.

라이브러리 디자인은 광범위한 기능 집합에 비해 높은 성능과 낮은 메모리 할당을 강조합니다. 기본 제공 UTF-8 지원은 UTF-8로 인코딩된 JSON 텍스트를 읽고 쓰는 프로세스를 최적화합니다. 이는 웹의 데이터와 디스크의 파일에 가장 널리 사용되는 인코딩입니다.

라이브러리는 메모리 내 DOM(문서 개체 모델)을 사용하기 위한 클래스도 제공합니다. 이 기능을 사용하면 JSON 파일 또는 문자열의 요소에 대한 임의 읽기 전용 액세스가 가능합니다.

## <a name="how-to-get-the-library"></a>라이브러리를 가져오는 방법

* 라이브러리는 .NET Core 3.0 이상 버전에서 공유 프레임워크의 일부로 기본 제공됩니다.
* 이전 프레임워크 버전의 경우 [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치하세요. 패키지는 다음을 지원합니다.

  * .NET Standard 2.0 이상 버전
  * .NET Framework 4.7.2 이상 버전
  * .NET Core 2.0, 2.1 및 2.2

## <a name="additional-resources"></a>추가 자료

* [라이브러리를 사용하는 방법](system-text-json-how-to.md)
* [JsonSerializerOptions 인스턴스 인스턴스화](system-text-json-configure-options.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [참조 유지](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션](system-text-json-migrate-from-newtonsoft-how-to.md)
* [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)
* [사용자 지정 직렬 변환기 및 역직렬 변환기 작성](write-custom-serializer-deserializer.md)
* [JSON serialization용 사용자 지정 변환기 작성](system-text-json-converters-how-to.md)
* [DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
* [System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)
