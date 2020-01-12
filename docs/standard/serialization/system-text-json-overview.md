---
title: -.Net을 사용 하 C# 여 JSON Serialize 및 deserialize
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c05783963ba521109fb542f247ec9e62fdb5c2d9
ms.sourcegitcommit: dfad244ba549702b649bfef3bb057e33f24a8fb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2020
ms.locfileid: "75904637"
---
# <a name="json-serialization-and-deserialization-marshalling-and-unmarshalling-in-net---overview"></a>.NET의 JSON serialization 및 deserialization (마샬링 및 마샬링 안)-개요

`System.Text.Json` 네임 스페이스는 JSON (JavaScript Object Notation)로 serialize 및 deserialize 하는 기능을 제공 합니다.

라이브러리 디자인은 광범위 한 기능 집합에 대 한 높은 성능 및 낮은 메모리 할당을 강조 합니다. UTF-8 지원은 UTF-8로 인코딩된 JSON 텍스트를 읽고 쓰는 프로세스를 최적화 합니다 .이는 웹의 데이터와 디스크의 파일에 대해 가장 널리 알려진 인코딩입니다.

또한 라이브러리는 메모리 내 DOM (문서 개체 모델)을 사용 하기 위한 클래스를 제공 합니다. 이 기능을 사용 하면 JSON 파일이 나 문자열의 요소에 대해 임의의 읽기 전용 액세스를 사용할 수 있습니다. 

## <a name="how-to-get-the-library"></a>라이브러리를 가져오는 방법

* 라이브러리는 [.Net Core 3.0](https://aka.ms/netcore3download) 공유 프레임 워크의 일부로 기본 제공 됩니다.
* 다른 대상 프레임 워크의 경우에는 [System.object](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치 합니다. 패키지는 다음을 지원 합니다.
  * .NET Standard 2.0 이상 버전
  * .NET Framework 4.7.2 이상 버전
  * .NET Core 2.0, 2.1 및 2.2

## <a name="additional-resources"></a>추가 자료

* [라이브러리를 사용 하는 방법](system-text-json-how-to.md)
* [Newtonsoft.json에서 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md)
* [변환기를 작성 하는 방법](system-text-json-converters-how-to.md)
* [System.string 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json)
* [System.object API 참조](xref:System.Text.Json)
* [System.string API 참조](xref:System.Text.Json.Serialization)
<!-- * [Roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
