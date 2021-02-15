---
description: '자세한 정보: 방법: 매개 변수를 무제한으로 사용 하는 프로시저 오버 로드 (Visual Basic)'
title: '방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 97e391c2981760e012d56e1f93c24eb60ce3ebfe
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100460048"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a>방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드(Visual Basic)

프로시저에 [ParamArray](../../../language-reference/modifiers/paramarray.md) 매개 변수가 있는 경우 매개 변수 배열에 1 차원 배열을 가져오는 오버 로드 된 버전을 정의할 수 없습니다. 자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)에서 "ParamArray 매개 변수에 대 한 암시적 오버 로드"를 참조 하십시오.  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a>가변적인 개수의 매개 변수를 사용 하는 프로시저를 오버 로드 하려면  
  
1. 프로시저와 호출 코드 논리가 매개 변수에서 오버 로드 된 버전 보다 더 많은 이점을 제공 하는지 확인 합니다 `ParamArray` . [오버 로드 프로시저에서 고려할 사항은](./considerations-in-overloading-procedures.md)"오버 로드 및 paramarrays"를 참조 하십시오.  
  
2. 프로시저에서 매개 변수 목록의 변수 부분에 허용 해야 하는 제공 된 값의 개수를 확인 합니다. 여기에는 값이 없는 경우이 포함 될 수 있으며, 1 차원 배열의 대/소문자가 포함 될 수도 있습니다.  
  
3. 제공 된 값의 허용 되는 개수에는 `Sub` `Function` 해당 하는 매개 변수 목록을 정의 하는 또는 선언문을 작성 합니다. `Optional` `ParamArray` 이 오버 로드 된 버전에서 또는 키워드를 사용 하지 마세요.  
  
4. 각 선언에서 `Sub` 또는 키워드 앞에 `Function` [Overloads](../../../language-reference/modifiers/overloads.md) 키워드를 붙입니다.  
  
5. 각 선언 후에 호출 코드에서 해당 선언의 매개 변수 목록에 해당 하는 값을 제공할 때 실행 되어야 하는 프로시저 코드를 작성 합니다.  
  
6. 또는 문을 사용 하 여 각 프로시저를 적절 하 게 종료 `End Sub` `End Function` 합니다.  
  
## <a name="example"></a>예  

 다음 예에서는 [ParamArray](../../../language-reference/modifiers/paramarray.md) 매개 변수를 사용 하 여 정의 된 프로시저와 해당 하는 오버 로드 된 프로시저 집합을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 매개 변수 배열에 1 차원 배열을 사용 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다. 그러나 다른 암시적 오버 로드의 시그니처를 사용할 수 있습니다. 다음 선언에서는이를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 오버 로드 된 버전의 코드는 호출 코드에서 매개 변수에 대해 하나 이상의 값을 제공 했는지 여부를 테스트 하지 않아도 `ParamArray` 됩니다. Visual Basic 호출 하는 인수 목록과 일치 하는 버전으로 제어를 전달 합니다.  
  
## <a name="compile-the-code"></a>코드 컴파일  

 매개 변수가 있는 프로시저는 `ParamArray` 오버 로드 된 버전 집합과 동일 하므로 이러한 암시적 오버 로드에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다. 자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)을 참조 하세요.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  

 무한정 클 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량을 overrunning 위험이 있습니다. 매개 변수 배열을 허용 하는 경우, 호출 코드가 전달 된 배열의 길이를 테스트 하 고, 응용 프로그램에 비해 너무 클 경우 적절 한 단계를 수행 해야 합니다.  
  
## <a name="see-also"></a>추가 정보

- [절차](./index.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [선택적 매개 변수](./optional-parameters.md)
- [매개 변수 배열](./parameter-arrays.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [프로시저 문제 해결](./troubleshooting-procedures.md)
- [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)
- [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)
- [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Overload Resolution](./overload-resolution.md)
