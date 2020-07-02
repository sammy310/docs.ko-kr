---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615647"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter가 `<br/>` 요소를 올바르게 렌더링하지 않음

#### <a name="details"></a>세부 정보

.NET Framework 4.6부터 `<BR />` 요소로 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> 및 <xref:System.Web.UI.HtmlTextWriter.RenderEndTag>를 호출하면 (두 개가 아닌) 단 하나의 `<BR />`만 올바르게 삽입합니다.

#### <a name="suggestion"></a>제안 해결 방법

응용 프로그램이 추가 `<BR />` 태그에 종속된 경우 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)>를 두 번째로 호출해야 합니다. 이 동작 변경은 .NET Framework 4.6 이상을 대상으로 하는 응용 프로그램에만 영향을 주므로 다른 옵션은 이전 버전의 .NET Framework를 대상으로 하여 이전 동작을 가져오는 것입니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
