---
title: 동적 개체 작업
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 20d007fb48e1db352bab6d8e25d2e60e02554732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345171"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>동적 개체 작업(Visual Basic)
동적 개체는 런타임에 개체에 바인딩하기 위해 `Object` 형식이 아닌 또 다른 방법을 제공 합니다. 동적 개체는 <xref:System.Dynamic> 네임 스페이스에 정의 된 동적 인터페이스를 사용 하 여 런타임에 속성 및 메서드와 같은 멤버를 노출 합니다. <xref:System.Dynamic> 네임 스페이스의 클래스를 사용 하 여 정적 형식이 나 형식과 일치 하지 않는 데이터 구조를 사용 하는 개체를 만들 수 있습니다. 또한 IronPython 및 IronRuby와 같은 동적 언어에서 정의 된 동적 개체를 사용할 수 있습니다. 동적 개체를 만들거나 동적 언어로 정의 된 동적 개체를 사용 하는 방법을 보여 주는 예제는 [연습: 동적 개체 만들기 및 사용](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>또는 <xref:System.Dynamic.ExpandoObject>을 참조 하세요.  
  
 Visual Basic는 <xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스를 사용 하 여 동적 언어 런타임의 개체와 IronPython 및 IronRuby와 같은 동적 언어에 바인딩합니다. `IDynamicMetaObjectProvider` 인터페이스를 구현 하는 클래스의 예로는 <xref:System.Dynamic.DynamicObject> 및 <xref:System.Dynamic.ExpandoObject> 클래스가 있습니다.  
  
 런타임에 바인딩된 호출이 `IDynamicMetaObjectProvider` 인터페이스를 구현 하는 개체에 대해 수행 되는 경우 Visual Basic는 해당 인터페이스를 사용 하 여 동적 개체에 바인딩합니다. `IDynamicMetaObjectProvider` 인터페이스를 구현 하지 않는 개체에 대 한 런타임에 바인딩된 호출이 수행 되거나 `IDynamicMetaObjectProvider` 인터페이스에 대 한 호출이 실패 하는 경우 Visual Basic 런타임의 런타임에 바인딩 기능을 사용 하 여 개체에 바인딩합니다 Visual Basic.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [연습: 동적 개체 만들기 및 사용](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [초기 바인딩 및 런타임에 바인딩](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
