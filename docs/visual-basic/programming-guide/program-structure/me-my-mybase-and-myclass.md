---
title: Me, My, MyBase 및 MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401432"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic의 Me, My, MyBase 및 MyClass
`Me``MyBase`및 `My`Visual `MyClass` Basic의 이름은 비슷하지만 목적은 다릅니다. 이 항목에서는 이러한 엔터티를 구분하기 위해 이러한 각 엔터티에 대해 설명합니다.  
  
## <a name="me"></a>본인  
 키워드는 `Me` 코드가 현재 실행 중인 클래스 또는 구조의 특정 인스턴스를 참조하는 방법을 제공합니다. `Me`현재 인스턴스를 참조하는 개체 변수 또는 구조 변수처럼 행동합니다. 사용 `Me` 은 클래스 또는 구조자의 현재 실행 중인 인스턴스에 대한 정보를 다른 클래스, 구조또는 모듈의 프로시저에 전달하는 데 특히 유용합니다.  
  
 예를 들어 모듈에 다음 절차가 있다고 가정합니다.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 다음 문을 사용 하 여이 프로시저를 호출 하 고 인수로 <xref:System.Windows.Forms.Form> 클래스의 현재 인스턴스를 전달할 수 있습니다.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 이 `My` 기능을 사용하면 여러 .NET Framework 클래스에 쉽고 직관적으로 액세스할 수 있으므로 Visual Basic 사용자가 컴퓨터, 응용 프로그램, 설정, 리소스 등과 상호 작용할 수 있습니다.  
  
## <a name="mybase"></a>MyBase  
 키워드는 `MyBase` 클래스의 현재 인스턴스의 기본 클래스를 참조하는 개체 변수처럼 행동합니다. `MyBase`일반적으로 파생 클래스에서 재정의되거나 그림자가 있는 기본 클래스 멤버에 액세스하는 데 사용됩니다. `MyBase.New`파생 된 클래스 생성자에서 base 클래스 생성자 명시적으로 호출 하는 데 사용 됩니다.  
  
## <a name="myclass"></a>MyClass  
 키워드는 `MyClass` 원래 구현된 클래스의 현재 인스턴스를 참조하는 개체 변수처럼 실행됩니다. `MyClass``Me`과 비슷하지만 모든 메서드 호출은 메서드가 `NotOverridable`있는 것처럼 처리됩니다.  
  
## <a name="see-also"></a>참고 항목

- [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
