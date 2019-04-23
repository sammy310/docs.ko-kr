---
title: '방법: 개인 글꼴 컬렉션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: f78d48c88b72388676f5e7ae963b98d8f1b4beac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210693"
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="09738-102">방법: 개인 글꼴 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="09738-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="09738-103">합니다 <xref:System.Drawing.Text.PrivateFontCollection> 클래스에서 상속 된 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="09738-104">사용할 수는 <xref:System.Drawing.Text.PrivateFontCollection> 응용 프로그램에 맞게 글꼴 집합도 유지 관리 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="09738-105">개인 글꼴 컬렉션 컴퓨터에 설치 되지 않은 글꼴 뿐만 아니라 설치 된 시스템 글꼴을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09738-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="09738-106">글꼴 파일을 개인 글꼴 컬렉션에 추가할 호출을 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> 메서드를 <xref:System.Drawing.Text.PrivateFontCollection> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="09738-107">합니다 <xref:System.Drawing.Text.FontCollection.Families%2A> 의 속성을 <xref:System.Drawing.Text.PrivateFontCollection> 개체의 배열을 포함 <xref:System.Drawing.FontFamily> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="09738-108">개인 글꼴 컬렉션에서 글꼴 패밀리 수가 아닐 컬렉션에 추가 된 글꼴 파일의 수와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="09738-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="09738-109">예를 들어, 컬렉션에 ArialBd.tff, Times.tff, 및 TimesBd.tff 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="09738-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="09738-110">됩니다 파일 세 개 있지만 컬렉션에 있는 두 패밀리 Times.tff 및 TimesBd.tff 동일한 제품군에 속해 있으므로.</span><span class="sxs-lookup"><span data-stu-id="09738-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09738-111">예제</span><span class="sxs-lookup"><span data-stu-id="09738-111">Example</span></span>  
 <span data-ttu-id="09738-112">다음 예제에서는 다음 세 개의 글꼴 파일을 <xref:System.Drawing.Text.PrivateFontCollection> 개체:</span><span class="sxs-lookup"><span data-stu-id="09738-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
-   <span data-ttu-id="09738-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, 일반)</span><span class="sxs-lookup"><span data-stu-id="09738-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
-   <span data-ttu-id="09738-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New 굵게 기울임꼴)</span><span class="sxs-lookup"><span data-stu-id="09738-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
-   <span data-ttu-id="09738-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman 굵게 표시)</span><span class="sxs-lookup"><span data-stu-id="09738-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="09738-116">코드의 배열을 검색 <xref:System.Drawing.FontFamily> 에서 개체를 <xref:System.Drawing.Text.FontCollection.Families%2A> 의 속성을 <xref:System.Drawing.Text.PrivateFontCollection> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="09738-117">각 <xref:System.Drawing.FontFamily> 코드를 호출 하 여 컬렉션에서 개체를 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> (일반, 굵게, 기울임꼴, 굵게 기울임꼴, 밑줄 및 취소선) 다양 한 스타일을 사용할 수 있는지 여부를 결정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="09738-118">인수에 전달 합니다 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 의 멤버인 메서드는 <xref:System.Drawing.FontStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="09738-119">지정 된 제품군/스타일 조합을 사용할 수 있으면를 <xref:System.Drawing.Font> 개체는 패밀리 및 스타일을 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09738-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="09738-120">전달 된 첫 번째 인수는 <xref:System.Drawing.Font.%23ctor%2A> 생성자는 글꼴 패밀리 이름을 (하지는 <xref:System.Drawing.FontFamily> 의 다른 변형에 대 한 경우 개체는 <xref:System.Drawing.Font.%23ctor%2A> 생성자).</span><span class="sxs-lookup"><span data-stu-id="09738-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="09738-121">후는 <xref:System.Drawing.Font> 개체가 생성 되 면 전달 되는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드의 <xref:System.Drawing.Graphics> 클래스 스타일의 이름과 함께 제품군 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="09738-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="09738-122">다음 코드의 출력은 다음 그림에 표시 된 출력과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="09738-122">The output of the following code is similar to the output shown in the following illustration:</span></span>  
  
 ![다양 한 글꼴의 텍스트를 보여 주는 스크린샷.](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 <span data-ttu-id="09738-124">(다음 코드 예제에서 개인 글꼴 컬렉션에 추가 된)는 Arial.tff에 Arial 보통 스타일에 대 한 글꼴 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="09738-125">그러나는 프로그램 출력 Arial 글꼴 패밀리에 대 한 일반 이외의 여러 사용 가능한 스타일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09738-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="09738-126">있기 때문입니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 일반 스타일에서 굵게, 기울임꼴 및 굵은 기울임꼴 스타일을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09738-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="09738-127">일반 스타일에서 밑줄과 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09738-127">can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="09738-128">마찬가지로, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 를 굵게 또는 기울임꼴 스타일에서 굵게 기울임꼴 스타일을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09738-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="09738-129">굵은 기울임꼴 스타일 되 번 제품군에 사용할 수 있는 유일한 TimesBd.tff (Times New Roman 굵게 표시 된) 경우에 프로그램 출력에 표시 컬렉션에 있는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="09738-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09738-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="09738-130">Compiling the Code</span></span>  
 <span data-ttu-id="09738-131">앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="09738-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09738-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="09738-132">See also</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection>
- [<span data-ttu-id="09738-133">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="09738-133">Using Fonts and Text</span></span>](using-fonts-and-text.md)
