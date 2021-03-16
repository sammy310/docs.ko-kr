---
title: 복사 생성자를 작성하는 방법 - C# 프로그래밍 가이드
description: C#에서 클래스의 인스턴스를 가져와서 입력 값으로 새 인스턴스를 반환하는 복사 생성자를 작성하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: c61018444dd600d6f33765b104034355d0301667
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255238"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>복사 생성자를 작성하는 방법(C# 프로그래밍 가이드)

C# [레코드](records.md)는 개체의 복사 생성자를 제공하지만 클래스의 경우 직접 작성해야 합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서 `Person`[클래스](../../language-reference/keywords/class.md)는 `Person` 인스턴스를 해당 인수로 사용하는 복사 생성자를 정의합니다. 인수의 속성 값이 `Person`의 새 인스턴스 속성에 할당됩니다. 코드에는 복사하려는 인스턴스의 `Name` 및 `Age` 속성을 클래스의 인스턴스 생성자에 보내는 대체 복사 생성자가 포함되어 있습니다.  
  
 [!code-csharp[CopyConstructor](snippets/how-to-write-a-copy-constructor/Program.cs)]

## <a name="see-also"></a>참고 항목

- <xref:System.ICloneable>
- [레코드](records.md)
- [C# 프로그래밍 가이드](../index.md)
- [클래스 및 구조체](./index.md)
- [생성자](./constructors.md)
- [종료자](./destructors.md)
