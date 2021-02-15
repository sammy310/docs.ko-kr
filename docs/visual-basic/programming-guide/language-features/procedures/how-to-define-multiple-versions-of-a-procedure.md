---
description: '자세히 알아보기: 방법: 여러 버전의 프로시저 정의 (Visual Basic)'
title: '방법: 여러 버전의 프로시저 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: 4b470e478c22c3a827f71b9b28056e16d6d9b7cd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456031"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>방법: 여러 버전의 프로시저 정의(Visual Basic)

각 버전에 대해 동일한 이름을 사용 하 고 다른 매개 변수 목록을 사용 *하 여 프로시저* 를 여러 버전으로 정의할 수 있습니다. 오버 로드의 목적은 프로시저를 이름으로 구분 하지 않고도 긴밀 하 게 관련 된 여러 버전을 정의 하는 것입니다.  
  
 자세한 내용은 [Procedure Overloading](./procedure-overloading.md)을 참조하세요.  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>프로시저의 여러 버전을 정의 하려면  
  
1. 정의 하려는 `Sub` `Function` 프로시저의 각 버전에 대 한 또는 선언문을 작성 합니다. 모든 선언에 동일한 프로시저 이름을 사용 합니다.  
  
2. `Sub` `Function` 각 선언의 또는 키워드 앞에 [Overloads](../../../language-reference/modifiers/overloads.md) 키워드를 사용 합니다. 필요에 따라 선언에서 생략할 수 있지만 선언에 `Overloads` 포함 하는 경우 모든 선언에 포함 해야 합니다.  
  
3. 각 선언 문 다음에 호출 코드가 해당 버전의 매개 변수 목록과 일치 하는 인수를 제공 하는 특정 사례를 처리 하는 프로시저 코드를 작성 합니다. 호출 코드에서 제공 하는 매개 변수를 테스트할 필요가 없습니다. Visual Basic는 프로시저의 일치 하는 버전으로 제어를 전달 합니다.  
  
4. 또는 문을 사용 하 여 프로시저의 각 버전을 적절 하 게 종료 `End Sub` `End Function` 합니다.  
  
## <a name="example"></a>예  

 다음 예에서는 `Sub` 고객의 잔액에 대해 트랜잭션을 게시 하는 프로시저를 정의 합니다. 키워드를 사용 하 여 `Overloads` 두 가지 버전의 프로시저를 정의 합니다. 하나는 이름으로 고객을 수락 하 고 다른 하나는 계정 번호로 지정 합니다.  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
 호출 하는 코드는 또는로 고객 id를 가져온 `String` `Integer` 다음 두 경우 모두 동일한 호출 문을 사용할 수 있습니다.  
  
 이러한 버전의 프로시저를 호출 하는 방법에 대 한 자세한 내용은 `post` [방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)을 참조 하세요.  
  
## <a name="compile-the-code"></a>코드 컴파일  

 오버 로드 된 각 버전에 동일한 프로시저 이름이 있지만 다른 매개 변수 목록이 있는지 확인 합니다.  
  
## <a name="see-also"></a>추가 정보

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [프로시저 오버로드에서 고려해야 할 사항](./considerations-in-overloading-procedures.md)
- [Overload Resolution](./overload-resolution.md)
