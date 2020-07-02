---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614719"
---
### <a name="path-colon-checks-are-stricter"></a>경로 콜론 검사가 더욱 엄격해짐

#### <a name="details"></a>설명

.NET Framework 4.6.2에서 이전에 지원되지 않던 경로(길이 및 형식 모두)를 지원하도록 여러 가지가 변경되었습니다. 적절한 드라이브 구분 기호(콜론) 구문에 대해 검사가 좀 더 정확해졌습니다. 이 구문은 허용되었던 일부 선택 경로 API에서 일부 URI 경로가 차단되는 부작용이 있었습니다.

#### <a name="suggestion"></a>제안 해결 방법

영향을 받는 API로 URI를 전달하는 경우 먼저 합법적인 경로가 되도록 문자열을 수정합니다.<ul><li>URL에서 스키마를 수동으로 제거합니다(예: URL에서 `file://` 제거).

- URI를 <xref:System.Uri> 클래스에 전달하고 <xref:System.Uri.LocalPath>를 사용합니다.

또는 `Switch.System.IO.UseLegacyPathHandling` AppContext 스위치를 true로 설정하여 새 경로 정규화를 옵트아웃합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
