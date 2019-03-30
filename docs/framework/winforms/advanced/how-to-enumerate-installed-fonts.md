---
title: '방법: 설치 된 글꼴 열거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: e56f06d6f7a762a1ef1ff85fa30751ea64f9f14b
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653745"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="3cb92-102">방법: 설치 된 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="3cb92-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="3cb92-103">합니다 <xref:System.Drawing.Text.InstalledFontCollection> 클래스에서 상속 된 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="3cb92-104">사용할 수는 <xref:System.Drawing.Text.InstalledFontCollection> 컴퓨터에 설치 된 글꼴을 열거 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="3cb92-105">합니다 <xref:System.Drawing.Text.FontCollection.Families%2A> 의 속성을 <xref:System.Drawing.Text.InstalledFontCollection> 개체의 배열이 <xref:System.Drawing.FontFamily> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb92-106">예제</span><span class="sxs-lookup"><span data-stu-id="3cb92-106">Example</span></span>  
 <span data-ttu-id="3cb92-107">다음 예제에서는 컴퓨터에 설치 하는 모든 글꼴 패밀리 이름을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="3cb92-108">코드를 검색 합니다 <xref:System.Drawing.FontFamily.Name%2A> 의 각 속성 <xref:System.Drawing.FontFamily> 반환한 배열의 개체에에서는 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="3cb92-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="3cb92-109">제품군 이름 검색은 쉼표로 구분 된 형식 목록에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="3cb92-110">그런 다음 <xref:System.Drawing.Graphics.DrawString%2A> 메서드는 <xref:System.Drawing.Graphics> 클래스 쉼표로 구분 된 목록 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="3cb92-111">예제 코드를 실행 하는 경우 다음 그림에 나와 있는 것과 비슷한 출력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![설치 된 글꼴 패밀리를 보여주는 스크린샷.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3cb92-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3cb92-113">Compiling the Code</span></span>  
 <span data-ttu-id="3cb92-114">앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="3cb92-115">또한 가져와야는 <xref:System.Drawing.Text> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3cb92-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb92-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="3cb92-116">See also</span></span>
- [<span data-ttu-id="3cb92-117">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="3cb92-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
