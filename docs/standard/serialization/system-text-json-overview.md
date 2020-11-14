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
ms.openlocfilehash: d8bd5bcf78db534bd722972db01253cbd13a7a06
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282404"
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
* [Newtonsoft.Json에서 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md)
* [변환기를 작성하는 방법](system-text-json-converters-how-to.md)
* [System.Text.Json 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [System.Text.Json API 참조](xref:System.Text.Json)
* [System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
