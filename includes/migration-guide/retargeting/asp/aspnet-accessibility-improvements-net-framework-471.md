---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614683"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a>.NET Framework 4.7.1의 ASP.NET 액세스 가능성 향상

#### <a name="details"></a>설명

.NET Framework 4.7.1부터 ASP.NET은 ASP.NET 웹 컨트롤이 Visual Studio의 액세스 가능성 기술과 연동하는 방식을 개선하여 ASP.NET 고객을 보다 잘 지원하도록 했습니다.  여기에는 다음과 같은 변경이 포함됩니다.

- 자세히 보기 마법사의 필드 추가 대화 상자 또는 ListView 마법사의 ListView 구성 대화 상자와 같이 컨트롤에서 누락된 UI 액세스 가능성 패턴을 구현하도록 변경됨.
- 데이터 호출기 필드 편집기와 같이 고대비 모드에서 디스플레이를 개선하도록 변경됨.
- DataPager 컨트롤의 [호출기 필드 편집] 마법사의 [필드] 대화 상자, [ObjectContext 구성] 대화 상자 또는 [데이터 원본 구성] 마법사의 [데이터 선택 구성] 대화 상자와 같은 컨트롤의 키보드 탐색 환경을 개선하도록 변경됨.

#### <a name="suggestion"></a>제안 해결 방법

**이러한 변경을 선택/해제하는 방법** Visual Studio 디자이너에서 이러한 변경의 이점을 얻으려면 .NET Framework 4.7.1 이상에서 실행해야 합니다. 웹 애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.

- 기본적으로 다음 AppContext 스위치를 사용하여 새로운 액세스 가능성 기능을 지원하는 Visual Studio 2017 15.3 이상을 설치합니다.
- 다음 예제와 같이 devenv.exe.config 파일의 `<runtime>` 섹션에 `Switch.UseLegacyAccessibilityFeatures` AppContext 스위치를 추가하고 이를 `false`로 설정하여 레거시 액세스 가능성 동작을 옵트아웃합니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

.NET Framework 4.7.1 이상을 대상으로 하고 레거시 액세스 가능성 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 레거시 액세스 가능성 기능 사용을 옵트인할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.1       |
| 형식    | 대상 변경 |
