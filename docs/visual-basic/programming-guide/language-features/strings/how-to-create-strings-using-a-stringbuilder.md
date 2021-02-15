---
description: '자세히 알아보기: 방법: Visual Basic StringBuilder를 사용 하 여 문자열 만들기'
title: '방법: StringBuilder를 사용 하 여 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 6def32517f71ec3c2a7795c3395e3e572903ce1e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429821"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>방법: Visual Basic StringBuilder를 사용 하 여 문자열 만들기

이 예제에서는 클래스를 사용 하 여 여러 개의 작은 문자열에서 긴 문자열을 생성 <xref:System.Text.StringBuilder> 합니다. <xref:System.Text.StringBuilder>클래스는 `&=` 여러 문자열을 연결 하기 위한 연산자 보다 더 효율적입니다.

## <a name="example"></a>예

다음 예제에서는 클래스의 인스턴스를 만들고 <xref:System.Text.StringBuilder> 해당 인스턴스에 1000 문자열을 추가한 다음 해당 문자열 표현을 반환 합니다.

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>추가 정보

- [StringBuilder 클래스 사용](../../../../standard/base-types/stringbuilder.md)
- [&= 연산자](../../../language-reference/operators/and-assignment-operator.md)
- [문자열](index.md)
- [새 문자열 만들기](../../../../standard/base-types/creating-new.md)
- [문자열 조작](../../../../standard/base-types/best-practices-strings.md)
