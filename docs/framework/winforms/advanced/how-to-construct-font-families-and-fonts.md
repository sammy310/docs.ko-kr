---
title: '방법: 글꼴 패밀리 및 글꼴 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 84c3cd07ec27c7ce000962e14801ac171a6bba8c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648287"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="0179c-102">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="0179c-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="0179c-103">글꼴 서체 하지만 다양 한 스타일을 사용 하 여 글꼴 패밀리로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-103">groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="0179c-104">예를 들어, 굴림 글꼴 패밀리에는 다음 글꼴을 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-104">For example, the Arial font family contains the following fonts:</span></span>  
  
- <span data-ttu-id="0179c-105">Arial 일반</span><span class="sxs-lookup"><span data-stu-id="0179c-105">Arial Regular</span></span>  
  
- <span data-ttu-id="0179c-106">Arial 굵게</span><span class="sxs-lookup"><span data-stu-id="0179c-106">Arial Bold</span></span>  
  
- <span data-ttu-id="0179c-107">Arial 기울임꼴</span><span class="sxs-lookup"><span data-stu-id="0179c-107">Arial Italic</span></span>  
  
- <span data-ttu-id="0179c-108">Arial 굵은 기울임꼴</span><span class="sxs-lookup"><span data-stu-id="0179c-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="0179c-109">패밀리를 구성 하려면 네 가지 스타일을 사용 하 여: 일반, 굵게, 기울임꼴 및 굵은 기울임꼴 등입니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-109">uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="0179c-110">형용사와 같은 *범위를 좁힐* 하 고 *반올림* 스타일; 간주 되지 않습니다 이들은 제품군 이름 부분을 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="0179c-111">예를 들어, 굴림는 다음 멤버로 구성 된 글꼴 패밀리:</span><span class="sxs-lookup"><span data-stu-id="0179c-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
- <span data-ttu-id="0179c-112">Arial 좁은 일반</span><span class="sxs-lookup"><span data-stu-id="0179c-112">Arial Narrow Regular</span></span>  
  
- <span data-ttu-id="0179c-113">굵게 아미</span><span class="sxs-lookup"><span data-stu-id="0179c-113">Arial Narrow Bold</span></span>  
  
- <span data-ttu-id="0179c-114">Arial 좁은 기울임꼴</span><span class="sxs-lookup"><span data-stu-id="0179c-114">Arial Narrow Italic</span></span>  
  
- <span data-ttu-id="0179c-115">Arial 좁은 굵은 기울임꼴</span><span class="sxs-lookup"><span data-stu-id="0179c-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="0179c-116">사용 하 여 텍스트를 그리려면 먼저 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 구성 해야를 <xref:System.Drawing.FontFamily> 개체 및 <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="0179c-117"><xref:System.Drawing.FontFamily> 개체 (예: Arial) 서체를 지정 하며 <xref:System.Drawing.Font> 개체 크기, 스타일 및 단위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0179c-118">예제</span><span class="sxs-lookup"><span data-stu-id="0179c-118">Example</span></span>  
 <span data-ttu-id="0179c-119">다음 예제에서는 일반 스타일 Arial 글꼴 크기를 16 픽셀을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="0179c-120">다음 코드에서는 첫 번째 인수에 전달 합니다 <xref:System.Drawing.Font.%23ctor%2A> 생성자를 <xref:System.Drawing.FontFamily> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="0179c-121">두 번째 인수는 네 번째 인수에 의해 식별 되는 단위로 측정 되는 글꼴 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="0179c-122">세 번째 인수는 스타일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="0179c-123"><xref:System.Drawing.GraphicsUnit.Pixel> 멤버인 합니다 <xref:System.Drawing.GraphicsUnit> 열거형 및 <xref:System.Drawing.FontStyle.Regular> 멤버인는 <xref:System.Drawing.FontStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0179c-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0179c-124">Compiling the Code</span></span>  
 <span data-ttu-id="0179c-125">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0179c-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0179c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="0179c-126">See also</span></span>

- [<span data-ttu-id="0179c-127">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="0179c-127">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="0179c-128">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="0179c-128">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
