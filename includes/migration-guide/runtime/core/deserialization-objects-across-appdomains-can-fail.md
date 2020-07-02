---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620216"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>앱 도메인 간의 개체 역직렬화가 실패할 수 있습니다.

#### <a name="details"></a>설명

경우에 따라, 애플리케이션 기반이 다른 둘 이상의 앱 도메인이 앱에서 사용되는 경우 앱 도메인 간에 논리 호출 컨텍스트의 개체를 역직렬화하려고 하면 예외가 throw됩니다.

#### <a name="suggestion"></a>제안 해결 방법

[완화: 앱 도메인 간 개체의 deserialization](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)을 참조하세요.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5.1|
|형식|런타임|
