---
description: '자세한 정보: 기타 데이터 형식 (Visual Basic)'
title: 기타 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 3875a3fc3027d573013470cb96c9482a0be6cbbf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461998"
---
# <a name="miscellaneous-data-types-visual-basic"></a>기타 데이터 형식(Visual Basic)

Visual Basic는 숫자나 문자를 중심으로 하지 않는 여러 데이터 형식을 제공 합니다. 대신 예/아니요 값, 날짜/시간 값 및 개체 주소와 같은 특수 한 데이터를 처리 합니다.  
  
 Visual Basic 데이터 형식을 나란히 비교 하 여 보여 주는 표는 [데이터 형식](../../../language-reference/data-types/index.md)을 참조 하세요.  
  
## <a name="boolean-type"></a>부울 형식  

 [부울 데이터 형식은](../../../language-reference/data-types/boolean-data-type.md) 또는로 해석 되는 부호 없는 값입니다 `True` `False` . 데이터 너비는 구현 하는 플랫폼에 따라 달라 집니다. 변수에 true/false, 예/아니요 또는 설정/해제와 같은 두 가지 상태 값만 포함 될 수 있는 경우로 선언 `Boolean` 합니다.  
  
## <a name="date-type"></a>날짜 형식  

 날짜 [데이터 형식은](../../../language-reference/data-types/date-data-type.md) 날짜 및 시간 정보를 모두 포함 하는 64 비트 값입니다. 각 증가값은 그레고리오 력 달력에서 1 년 1 월 1 일의 시작 (12:00 AM) 이후 경과 된 시간 100 나노초를 나타냅니다. 변수에 날짜 값, 시간 값 또는 둘 다 포함 될 수 있는 경우로 선언 `Date` 합니다.  
  
## <a name="object-type"></a>개체 유형  

 [개체 데이터 형식은](../../../language-reference/data-types/object-data-type.md) 응용 프로그램이 나 다른 응용 프로그램 내에서 개체 인스턴스를 가리키는 32 비트 주소입니다. `Object`변수는 응용 프로그램에서 인식 하는 개체 또는 모든 데이터 형식의 데이터를 참조할 수 있습니다. 여기에는, 및 구조체 인스턴스와 같은 *값 형식과* 및 등의 `Integer` `Boolean` 클래스에서 만든 개체의 인스턴스인 *참조 형식이* 모두 포함 됩니다 `String` <xref:System.Windows.Forms.Form> .  
  
 변수가 컴파일 시간에 알 수 없는 클래스의 인스턴스에 대 한 포인터를 저장 하거나 다양 한 데이터 형식의 데이터를 가리킬 수 있는 경우로 선언 `Object` 합니다.  
  
 데이터 형식의 장점은 데이터 형식의 데이터 `Object` 를 저장 하는 데 사용할 수 있다는 것입니다. 단점은 실행 시간을 더 많이 사용 하 고 응용 프로그램을 느리게 수행 하는 추가 작업을 수행 하는 것입니다. `Object`값 형식에 대 한 변수를 사용 하는 경우 *boxing* 및 *unboxing* 을 발생 시킵니다. 참조 형식에 사용 하는 경우 *런타임에 바인딩이* 발생 합니다.  
  
## <a name="see-also"></a>추가 정보

- [형식 문자](type-characters.md)
- [기본 데이터 형식](elementary-data-types.md)
- [숫자 데이터 형식](numeric-data-types.md)
- [문자 데이터 형식](character-data-types.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [초기 바인딩 및 런타임에 바인딩](../early-late-binding/index.md)
