---
title: -.Net을 사용 하 C# 여 JSON Serialize 및 deserialize
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 6561d5e1580e1170369622ebc7bb330ff4e0964f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705784"
---
# <a name="json-serialization-in-net---overview"></a>.NET의 JSON serialization-개요

`System.Text.Json` 네임 스페이스는 JSON (JavaScript Object Notation)로 serialize 및 deserialize 하는 기능을 제공 합니다.

라이브러리 디자인은 광범위 한 기능 집합에 대 한 높은 성능 및 낮은 메모리 할당을 강조 합니다. UTF-8 지원은 UTF-8로 인코딩된 JSON 텍스트를 읽고 쓰는 프로세스를 최적화 합니다 .이는 웹의 데이터와 디스크의 파일에 대해 가장 널리 알려진 인코딩입니다.

또한 라이브러리는 메모리 내 DOM (문서 개체 모델)을 사용 하기 위한 클래스를 제공 합니다. 이 기능을 사용 하면 JSON 파일이 나 문자열의 요소에 대해 임의의 읽기 전용 액세스를 사용할 수 있습니다. 

## <a name="how-to-get-the-library"></a>라이브러리를 가져오는 방법

* 라이브러리는 [.Net Core 3.0](https://aka.ms/netcore3download) 공유 프레임 워크의 일부로 기본 제공 됩니다.
* 다른 대상 프레임 워크의 경우에는 [System.object](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치 합니다. 패키지는 다음을 지원 합니다.
  * .NET Standard 2.0 이상 버전
  * .NET Framework 4.6.1 이상 버전
  * .NET Core 2.0, 2.1 및 2.2

## <a name="additional-resources"></a>추가 자료

* [라이브러리를 사용 하는 방법](system-text-json-how-to.md)
* [소스 코드](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Text.Json)
* [API 참조](xref:System.Text.Json)
* [로드맵](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Text.Json/roadmap/README.md)
* Dotnet/corefx 리포지토리의 GitHub 문제
  * [System.object의 개발에 대 한 토론](https://github.com/dotnet/corefx/issues/33115) <!-- TODO: Issues are still not moved to the new repo-->
  * [모든 System.web. Json 문제](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json)
  * [Json 이라는 레이블이 지정 된 system.web 문제-doc](https://github.com/dotnet/runtime/labels/json-functionality-doc)
