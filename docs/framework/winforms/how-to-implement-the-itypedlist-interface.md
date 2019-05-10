---
title: '방법: ITypedList 인터페이스 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: 3f5a5032166087c7398d310071b3998c845e2780
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630743"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="e932d-102">방법: ITypedList 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="e932d-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="e932d-103">구현 된 <xref:System.ComponentModel.ITypedList> 인터페이스 바인딩 가능한 목록에 대 한 스키마 검색을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e932d-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e932d-104">예제</span><span class="sxs-lookup"><span data-stu-id="e932d-104">Example</span></span>  
 <span data-ttu-id="e932d-105">다음 코드 예제를 구현 하는 방법에 설명 합니다 <xref:System.ComponentModel.ITypedList> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e932d-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="e932d-106">라는 제네릭 형식은 `SortableBindingList` 에서 파생 되는 <xref:System.ComponentModel.BindingList%601> 클래스를 구현 합니다 <xref:System.ComponentModel.ITypedList> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e932d-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="e932d-107">이라는 간단한 클래스 `Customer` 의 헤더에 바인딩되는 데이터를 제공 된 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e932d-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e932d-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e932d-108">Compiling the Code</span></span>  
 <span data-ttu-id="e932d-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e932d-109">This example requires:</span></span>  
  
- <span data-ttu-id="e932d-110">System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e932d-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e932d-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="e932d-111">See also</span></span>

- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="e932d-112">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e932d-112">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
