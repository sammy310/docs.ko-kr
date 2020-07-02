---
title: '방법: INotifyPropertyChanged 인터페이스 구현'
description: Windows Forms 데이터 바인딩에 사용 되는 비즈니스 개체에서 INotifyPropertyChanged 인터페이스를 구현 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 83d2ef32787d2dbcd877bc77dcede10111098f8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619270"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>방법: INotifyPropertyChanged 인터페이스 구현
다음 코드 예제를 구현 하는 방법에 설명 합니다 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다. Windows Forms 데이터 바인딩에 사용 되는 비즈니스 개체에 대해이 인터페이스를 구현 합니다. 구현 되는 경우 인터페이스는 비즈니스 개체의 속성 변경 내용을 바인딩된 컨트롤에 전달 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>참고 항목

- [방법: PropertyNameChanged 패턴 적용](how-to-apply-the-propertynamechanged-pattern.md)
- [Windows Forms 데이터 바인딩](windows-forms-data-binding.md)
- [방법: BindingSource 및 INotifyPropertyChanged 인터페이스를 사용하여 변경 알림 발생](./controls/raise-change-notifications--bindingsource.md)
- [Windows Forms 데이터 바인딩의 변경 알림](change-notification-in-windows-forms-data-binding.md)
