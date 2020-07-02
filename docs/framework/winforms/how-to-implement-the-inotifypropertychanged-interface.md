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
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="2caf6-103">방법: INotifyPropertyChanged 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="2caf6-103">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="2caf6-104">다음 코드 예제를 구현 하는 방법에 설명 합니다 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2caf6-104">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="2caf6-105">Windows Forms 데이터 바인딩에 사용 되는 비즈니스 개체에 대해이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caf6-105">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="2caf6-106">구현 되는 경우 인터페이스는 비즈니스 개체의 속성 변경 내용을 바인딩된 컨트롤에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caf6-106">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2caf6-107">예제</span><span class="sxs-lookup"><span data-stu-id="2caf6-107">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2caf6-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2caf6-108">See also</span></span>

- [<span data-ttu-id="2caf6-109">방법: PropertyNameChanged 패턴 적용</span><span class="sxs-lookup"><span data-stu-id="2caf6-109">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="2caf6-110">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="2caf6-110">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="2caf6-111">방법: BindingSource 및 INotifyPropertyChanged 인터페이스를 사용하여 변경 알림 발생</span><span class="sxs-lookup"><span data-stu-id="2caf6-111">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="2caf6-112">Windows Forms 데이터 바인딩의 변경 알림</span><span class="sxs-lookup"><span data-stu-id="2caf6-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
