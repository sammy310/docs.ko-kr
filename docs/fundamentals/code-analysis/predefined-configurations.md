---
title: 미리 정의 된 구성 파일 (코드 분석)
description: 미리 정의 된 editorconfig 및 규칙 집합 파일을 사용 하 여 특정 유형의 코드 분석을 대상으로 지정 하는 방법에 대해 알아봅니다.
ms.date: 09/24/2020
ms.topic: conceptual
ms.openlocfilehash: 4937dcab1183fa3f63be4afc71627a7c7c08c6bd
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "96593136"
---
# <a name="predefined-configuration-files"></a>미리 정의 된 구성 파일

미리 정의 된 EditorConfig 및 [규칙 집합](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) 파일을 사용 하 여 보안 또는 디자인 규칙과 같은 코드 품질 규칙의 범주를 빠르고 쉽게 사용할 수 있습니다. 규칙의 특정 범주를 사용 하도록 설정 하면 대상 문제 및 특정 조건을 식별할 수 있습니다. 이러한 미리 정의 된 파일에 액세스 하려면 [Microsoft CodeAnalysis](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) NuGet analyzer 패키지를 설치 합니다.

[Microsoft CodeAnalysis .Net 분석기](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisnetanalyzers) 에는 다음 규칙 범주에 대 한 미리 정의 된 editorconfig 파일 및 규칙 집합이 포함 되어 있습니다.

- 모든 규칙
- 데이터 흐름
- 디자인
- 설명서
- 전역화
- 상호 운용성
- 유지 관리
- 이름 지정
- 성능
- FxCop에서 이식
- 안정성
- 보안
- 사용

이러한 각 규칙 범주에는 다음에 대 한 EditorConfig 또는 rule set 파일이 있습니다.

- 범주에 있는 모든 규칙을 사용 하도록 설정 하 고 다른 모든 규칙을 사용 하지 않도록 설정 합니다.
- 각 규칙의 기본 심각도를 사용 하 고 기본적으로 사용 하도록 설정 (및 다른 모든 규칙 사용 안 함)

> [!TIP]
> "모든 규칙" 범주에는 모든 규칙을 사용 하지 않도록 설정 하는 추가 EditorConfig 또는 규칙 집합 파일이 있습니다. 이 파일을 사용 하 여 프로젝트에서 분석기 경고 또는 오류를 신속 하 게 제거할 수 있습니다.

## <a name="predefined-editorconfig-files"></a>미리 정의 된 EditorConfig 파일

Microsoft CodeAnalysis. NetAnalyzers 분석기 패키지에 대해 미리 정의 된 EditorConfig 파일은 NuGet 패키지가 설치 된 *EditorConfig* 하위 디렉터리에 있습니다. 예를 들어 모든 보안 규칙을 사용 하도록 설정 하는 EditorConfig 파일은 *editorconfig/Securityrules enabled/.* e n t config에 있습니다.

선택한 *editorconfig* 파일을 프로젝트의 루트 디렉터리에 복사 합니다.

## <a name="predefined-rule-sets"></a>미리 정의된 규칙 집합

Microsoft CodeAnalysis. NetAnalyzers 분석기 패키지에 대 한 미리 정의 된 규칙 집합 파일은 NuGet 패키지가 설치 된 *의 규칙 집합 하위 디렉터리* 에 있습니다. 예를 들어 모든 보안 규칙을 사용 하도록 설정 하는 규칙 집합 파일은 규칙 집합/보안 규칙 *사용.* 규칙 집합에 있습니다. 하나 이상의 규칙 집합을 복사 하 여 프로젝트를 포함 하는 디렉터리에 붙여넣습니다.

## <a name="see-also"></a>참고 항목

- [분석기 구성](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [EditorConfig에 대 한 .NET 코드 스타일 규칙 옵션](code-style-rule-options.md)
