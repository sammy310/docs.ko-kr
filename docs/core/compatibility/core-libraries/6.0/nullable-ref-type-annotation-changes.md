---
title: '호환성이 손상되는 변경: Nullable 참조 형식 주석 변경 내용'
description: 일부 nullable 참조 형식 주석이 변경된 핵심 .NET 라이브러리의 .NET 6.0 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 02/11/2021
ms.openlocfilehash: a0133ce49ba33d0e835b718f3f2b19180526c61b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488224"
---
# <a name="changes-to-nullable-reference-type-annotations"></a>Nullable 참조 형식 주석의 변경 내용

.NET 6.0에서는 .NET 라이브러리의 일부 null 허용 여부 주석이 변경되었습니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 일부 nullable 참조 형식 주석이 잘못되었고 빌드 경고가 없거나 잘못되었습니다. .NET 6.0부터 이전에 적용된 일부 주석이 업데이트되었습니다. 새 빌드 경고가 생성되고 영향을 받는 API에 관한 잘못된 빌드 경고가 더 이상 생성되지 않습니다.

해당 변경 내용 중 일부는 새로운 빌드 시간 경고를 발생시킬 수 있기 때문에 ‘호환성이 손상되는 것’으로 간주합니다. .NET 6.0으로 마이그레이션하는 경우 해당 API를 참조하는 코드를 업데이트해야 합니다.

호환성이 손상되는 것으로 간주하지 않는 기타 변경 내용도 이 페이지에서 설명됩니다. 업데이트된 API를 참조하는 코드는 더 이상 필요하지 않은 연산자나 pragma를 제거하는 이점을 얻을 수 있습니다.

## <a name="version-introduced"></a>도입된 버전

6.0

## <a name="reason-for-change"></a>변경 이유

.NET Core 3.0부터 null 허용 여부 주석이 .NET 라이브러리에 적용되었습니다. 작업 시작부터 해당 주석의 실수가 예상되었습니다. 피드백 및 추가 테스트를 통해 영향을 받는 API의 nullable 주석은 부정확한 것으로 확인되었습니다. 업데이트된 주석은 API의 null 허용 여부 계약을 올바르게 나타냅니다.

## <a name="recommended-action"></a>권장 조치

수정된 null 허용 여부 계약을 반영하도록 해당 API를 호출하는 코드를 업데이트합니다.

## <a name="affected-apis"></a>영향을 받는 API

다음 표에서는 영향을 받는 API를 보여 줍니다.

| API | 변경 내용 | 호환성이 손상됨 또는 호환성이 손상되지 않음 | 추가된 버전 |
| - | - | - |
| <xref:System.ComponentModel.ISite.Container?displayProperty=nameWithType> | 속성 형식이 nullable임 | 주요 변경 | 미리 보기 1 |
| <xref:System.Xml.Linq.XContainer.Add(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XContainer.AddFirst(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XContainer.ReplaceNodes(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XDocument.%23ctor(System.Object[])> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XDocument.%23ctor(System.Xml.Linq.XDeclaration,System.Object[])> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XElement.%23ctor(System.Xml.Linq.XName,System.Object[])> | 두 번째 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XElement.ReplaceAll(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XElement.ReplaceAttributes(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XNode.AddAfterSelf(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XNode.AddBeforeSelf(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XNode.ReplaceWith(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XStreamingElement.%23ctor(System.Xml.Linq.XName,System.Object)> | 두 번째 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XStreamingElement.%23ctor(System.Xml.Linq.XName,System.Object[])> | 두 번째 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Xml.Linq.XStreamingElement.Add(System.Object[])?displayProperty=nameWithType> | 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Net.Http.HttpClient.PatchAsync%2A?displayProperty=nameWithType> | `content` 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Net.Http.HttpClient.PostAsync%2A?displayProperty=nameWithType> | `content` 매개 변수 형식이 nullable임  | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Net.Http.HttpClient.PutAsync%2A?displayProperty=nameWithType> | `content` 매개 변수 형식이 nullable임  | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Linq.Expressions.MethodCallExpression.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.Expression})?displayProperty=nameWithType> | 첫 번째 매개 변수 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Linq.Expressions.Expression%601.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.ParameterExpression})?displayProperty=nameWithType> | 반환 형식이 nullable임 | 호환성이 손상되지 않음 | 미리 보기 1 |
| <xref:System.Data.IDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> | `buffer` 매개 변수 형식이 nullable임 | 주요 변경 | 미리 보기 1 |
| <xref:System.Data.IDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType> | `buffer` 매개 변수 형식이 nullable임 | 주요 변경 | 미리 보기 1 |
| <xref:System.Data.Common.DbDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType> | `buffer` 매개 변수 형식이 nullable임 | 주요 변경 | 미리 보기 1 |
| <xref:System.Data.Common.DbDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType> | `buffer` 매개 변수 형식이 nullable임 | 주요 변경 | 미리 보기 1 |

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.ComponentModel.ISite.Container`
- `M:System.Xml.Linq.XContainer.Add(System.Object[])`
- `M:System.Xml.Linq.XContainer.AddFirst(System.Object[])`
- `M:System.Xml.Linq.XContainer.ReplaceNodes(System.Object[])`
- `M:System.Xml.Linq.XDocument.#ctor(System.Object[])`
- `M:System.Xml.Linq.XDocument.#ctor(System.Xml.Linq.XDeclaration,System.Object[])`
- `M:System.Xml.Linq.XElement.#ctor(System.Xml.Linq.XName,System.Object[])`
- `M:System.Xml.Linq.XElement.ReplaceAll(System.Object[])`
- `M:System.Xml.Linq.XElement.ReplaceAttributes(System.Object[])`
- `M:System.Xml.Linq.XNode.AddAfterSelf(System.Object[])`
- `M:System.Xml.Linq.XNode.AddBeforeSelf(System.Object[])`
- `M:System.Xml.Linq.XNode.ReplaceWith(System.Object[])`
- `M:System.Xml.Linq.XStreamingElement.#ctor(System.Xml.Linq.XName,System.Object)`
- `M:System.Xml.Linq.XStreamingElement.#ctor(System.Xml.Linq.XName,System.Object[])`
- `M:System.Xml.Linq.XStreamingElement.Add(System.Object[])`
- `O:System.Net.Http.HttpClient.PatchAsync`
- `O:System.Net.Http.HttpClient.PostAsync`
- `O:System.Net.Http.HttpClient.PutAsync`
- `M:System.Linq.Expressions.MethodCallExpression.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.Expression})`
- `M:System.Linq.Expressions.Expression%601.Update(System.Linq.Expressions.Expression,System.Collections.Generic.IEnumerable{System.Linq.Expressions.ParameterExpression})`
- `M:System.Data.IDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)`
- `M:System.Data.IDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)`
- `M:System.Data.Common.DbDataRecord.GetBytes(System.Int32,System.Int64,System.Byte[],System.Int32,System.Int32)`
- `M:System.Data.Common.DbDataRecord.GetChars(System.Int32,System.Int64,System.Char[],System.Int32,System.Int32)`

-->
