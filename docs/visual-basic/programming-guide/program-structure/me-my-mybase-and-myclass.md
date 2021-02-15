---
description: '에 대 한 자세한 정보: Me, My, MyBase 및 MyClass in Visual Basic'
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
ms.openlocfilehash: 04be6cc7063101a59838bf809731a66c27007283
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432795"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Visual Basic의 Me, My, MyBase 및 MyClass

`Me``My` `MyBase` Visual Basic의,, 및 `MyClass` 는 비슷한 이름을 갖지만 다른 용도로 사용 됩니다. 이 항목에서는 이러한 각 엔터티를 구별 하기 위해 설명 합니다.  
  
## <a name="me"></a>본인  

 `Me`키워드는 코드가 현재 실행 중인 클래스 또는 구조체의 특정 인스턴스를 참조 하는 방법을 제공 합니다. `Me` 현재 인스턴스를 참조 하는 개체 변수 또는 구조체 변수와 같은 동작을 수행 합니다. `Me`는 클래스 또는 구조체의 현재 실행 중인 인스턴스에 대 한 정보를 다른 클래스, 구조체 또는 모듈의 프로시저에 전달 하는 데 특히 유용 합니다.  
  
 예를 들어 모듈에 다음 절차가 있는 경우를 가정 합니다.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 다음 문을 사용 하 여이 프로시저를 호출 하 고 클래스의 현재 인스턴스를 인수로 전달할 수 있습니다 <xref:System.Windows.Forms.Form> .  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  

 이 `My` 기능은 다양 한 .NET Framework 클래스에 대 한 쉽고 직관적인 액세스를 제공 하 여 Visual Basic 사용자가 컴퓨터, 응용 프로그램, 설정, 리소스 등을 조작할 수 있도록 합니다.  
  
## <a name="mybase"></a>MyBase  

 `MyBase`키워드는 클래스의 현재 인스턴스에 대 한 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다. `MyBase` 는 파생 클래스에서 재정의 되거나 숨겨진 기본 클래스 멤버에 액세스 하는 데 일반적으로 사용 됩니다. `MyBase.New` 는 파생 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 사용 됩니다.  
  
## <a name="myclass"></a>MyClass  

 `MyClass`키워드는 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 동작 합니다. `MyClass` 는와 유사 `Me` 하지만이에 대 한 모든 메서드 호출은 메서드가 인 것 처럼 처리 됩니다 `NotOverridable` .  
  
## <a name="see-also"></a>추가 정보

- [상속 기본 사항](../language-features/objects-and-classes/inheritance-basics.md)
