---
description: '자세한 정보: 동적 개체 작업 (Visual Basic)'
title: 동적 개체 작업
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 4991ae3deca908fc0b96760f50c85514df92714f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434396"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>동적 개체 작업 (Visual Basic)

동적 개체는 형식 이외의 다른 방법을 제공 `Object` 하 여 런타임에 개체에 런타임에 바인딩합니다. 동적 개체는 네임 스페이스에 정의 된 동적 인터페이스를 사용 하 여 런타임에 속성 및 메서드와 같은 멤버를 노출 <xref:System.Dynamic> 합니다. 네임 스페이스의 클래스를 사용 <xref:System.Dynamic> 하 여 정적 형식 또는 형식과 일치 하지 않는 데이터 구조를 사용 하는 개체를 만들 수 있습니다. 또한 IronPython 및 IronRuby와 같은 동적 언어에서 정의 된 동적 개체를 사용할 수 있습니다. 동적 개체를 만들거나 동적 언어로 정의 된 동적 개체를 사용 하는 방법을 보여 주는 예제는 [연습: 동적 개체 만들기 및 사용](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), 또는를 참조 하세요 <xref:System.Dynamic.DynamicObject> <xref:System.Dynamic.ExpandoObject> .  
  
 Visual Basic는 인터페이스를 사용 하 여 동적 언어 런타임의 개체와 IronPython 및 IronRuby와 같은 동적 언어에 바인딩합니다 <xref:System.Dynamic.IDynamicMetaObjectProvider> . 인터페이스를 구현 하는 클래스의 예로는 `IDynamicMetaObjectProvider` <xref:System.Dynamic.DynamicObject> 및 <xref:System.Dynamic.ExpandoObject> 클래스가 있습니다.  
  
 인터페이스를 구현 하는 개체에 런타임에 바인딩된 호출이 수행 되는 경우 `IDynamicMetaObjectProvider` Visual Basic는 해당 인터페이스를 사용 하 여 동적 개체에 바인딩합니다. 인터페이스를 구현 하지 않는 개체에 대 한 런타임에 바인딩된 호출이 수행 `IDynamicMetaObjectProvider` 되거나 `IDynamicMetaObjectProvider` 인터페이스 호출이 실패 하면 Visual Basic Visual Basic 런타임의 런타임에 바인딩 기능을 사용 하 여 개체에 바인딩합니다.  
  
## <a name="see-also"></a>추가 정보

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [연습: 동적 개체 만들기 및 사용](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [초기 바인딩 및 런타임에 바인딩](index.md)
