---
ms.openlocfilehash: 1329a86db4227f75dfba7c50bbbdc2fc23099528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620279"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy는 문자열에 대상 열 인코딩을 사용함

#### <a name="details"></a>설명

열에 데이터를 삽입할 때 <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName>에서는 <code>VARCHAR</code> 및 <code>CHAR</code> 형식에 대한 기본 인코딩 대신 대상 열의 인코딩을 사용합니다. 이러한 변경을 통해 대상 열에서 기본 인코딩을 사용하지 않는 경우 기본 인코딩을 사용하여 발생하는 데이터 손상의 가능성을 제거합니다. 드문 경우이지만 인코딩에서의 이 변경으로 인해 대상 열에 맞추기에는 너무 큰 데이터가 생성되는 경우, 기존 애플리케이션에서 SqlException 예외를 throw할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

인코딩 차이로 인해 <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName>이 더 이상 데이터를 손상시키지 않을 것입니다. 대상 열의 크기 제한 근처 문자열을 복사하는 경우 데이터를 미리 인코딩(데이터가 대상 열에 맞는지 확인하기 위해 복사)하거나 <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>을 catch해야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)></li></ul>|
