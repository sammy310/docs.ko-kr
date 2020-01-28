---
title: BindingSource를 사용 하 여 컨트롤의 데이터 소스 업데이트 반영
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: f98296b477dbb674cdbdbd8d03e291dd6ca0c8a3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742443"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="20983-102">방법: BindingSource가 있는 Windows Forms 컨트롤에 데이터 소스 업데이트 내용 반영</span><span class="sxs-lookup"><span data-stu-id="20983-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="20983-103">데이터 바인딩된 컨트롤을 사용하는 경우 데이터 소스에서 목록 변경 이벤트가 발생하지 않을 때 데이터 소스의 변경 내용에 대응해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20983-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="20983-104"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 데이터 소스를 Windows Forms 컨트롤에 바인딩하는 경우 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 메서드를 호출하여 데이터 소스가 변경된 것을 컨트롤에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20983-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20983-105">예</span><span class="sxs-lookup"><span data-stu-id="20983-105">Example</span></span>  
 <span data-ttu-id="20983-106">다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 메서드를 사용하여 바인딩된 컨트롤에 데이터 소스 업데이트에 대해 알립니다.</span><span class="sxs-lookup"><span data-stu-id="20983-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20983-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="20983-107">Compiling the Code</span></span>  
 <span data-ttu-id="20983-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="20983-108">This example requires:</span></span>  
  
- <span data-ttu-id="20983-109">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="20983-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20983-110">참조</span><span class="sxs-lookup"><span data-stu-id="20983-110">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="20983-111">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="20983-111">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="20983-112">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="20983-112">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
