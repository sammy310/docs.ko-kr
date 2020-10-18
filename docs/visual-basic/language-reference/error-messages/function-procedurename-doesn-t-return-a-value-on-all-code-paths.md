---
title: "'<procedurename>' 함수가 일부 코드 경로에 대해서만 값을 반환합니다."
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 19b305e337767dfb34718aed7b665f142851bd36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163365"
---
# <a name="bc42105-function-procedurename-doesnt-return-a-value-on-all-code-paths"></a>BC42105: ' \<procedurename> ' 함수가 일부 코드 경로에 대 한 값을 반환 하지 않습니다.

' \<procedurename> ' 함수가 일부 코드 경로에 대해서만 값을 반환 합니다. ' Return ' 문이 있나요?

 `Function`프로시저에 해당 코드를 통해 값을 반환 하지 않는 경로가 하나 이상 있습니다.

 다음과 같은 방법으로 프로시저에서 값을 반환할 수 있습니다 `Function` .

- [반환 문에](../statements/return-statement.md)값을 포함 합니다.

- 프로시저 이름에 값을 할당 한 `Function` 다음 `Exit Function` 문을 수행 합니다.

- 프로시저 이름에 값을 할당 한 `Function` 다음 `End Function` 문을 수행 합니다.

 컨트롤이 또는로 전달 `Exit Function` `End Function` 되 고 프로시저 이름에 값을 할당 하지 않은 경우 프로시저는 반환 데이터 형식의 기본값을 반환 합니다. 자세한 내용은 [함수 문의](../statements/function-statement.md)"Behavior"를 참조 하십시오.

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC42105

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 제어 흐름 논리를 확인 하 고 반환을 발생 시키는 모든 문 앞에 값을 할당 해야 합니다.

     항상 문을 사용 하는 경우 프로시저의 모든 반환에서 값을 반환 하도록 보장 하는 것이 더 쉽습니다 `Return` . 이 작업을 수행 하는 경우 앞의 마지막 문이 문 이어야 합니다 `End Function` `Return` .

## <a name="see-also"></a>참고 항목

- [함수 프로시저](../../programming-guide/language-features/procedures/function-procedures.md)
- [Function 문](../statements/function-statement.md)
- [프로젝트 디자이너, 컴파일 페이지(Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
