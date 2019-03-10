---
title: '방법: PropertyNameChanged 패턴 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 889a7f5f7a84db378acaa88b717b6011f1a3dfdc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703480"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="07acb-102">방법: PropertyNameChanged 패턴 적용</span><span class="sxs-lookup"><span data-stu-id="07acb-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="07acb-103">다음 코드 예제를 적용 하는 방법에 설명 합니다 *PropertyName*패턴을 사용자 지정 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="07acb-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="07acb-104">Windows Forms 데이터 바인딩 엔진에서 사용 되는 사용자 지정 컨트롤을 구현 하는 경우이 패턴을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07acb-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07acb-105">예제</span><span class="sxs-lookup"><span data-stu-id="07acb-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="07acb-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="07acb-106">Compiling the Code</span></span>  
 <span data-ttu-id="07acb-107">이전 코드 예제를 컴파일하려면:</span><span class="sxs-lookup"><span data-stu-id="07acb-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="07acb-108">빈 코드 파일에 코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="07acb-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="07acb-109">포함 된 Windows Form에 사용자 지정 컨트롤을 사용 해야는 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="07acb-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07acb-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="07acb-110">See also</span></span>
- [<span data-ttu-id="07acb-111">방법: INotifyPropertyChanged 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="07acb-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="07acb-112">Windows Forms 데이터 바인딩의 변경 알림</span><span class="sxs-lookup"><span data-stu-id="07acb-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="07acb-113">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="07acb-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
