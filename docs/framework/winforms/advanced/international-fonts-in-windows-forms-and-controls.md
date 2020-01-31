---
title: 양식 및 컨트롤의 국제 글꼴
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743514"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="05564-102">Windows Forms 및 컨트롤의 국제 글꼴</span><span class="sxs-lookup"><span data-stu-id="05564-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="05564-103">국가별 응용 프로그램에서는 가능한 경우 글꼴 대체를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05564-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="05564-104">글꼴 대체 (fallback)는 시스템에서 문자가 속하는 스크립트를 결정 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="05564-105">글꼴 대체 사용</span><span class="sxs-lookup"><span data-stu-id="05564-105">Using font fallback</span></span>

<span data-ttu-id="05564-106">이 기능을 활용 하려면 폼 또는 다른 요소에 대 한 <xref:System.Drawing.Font> 속성을 설정 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="05564-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="05564-107">응용 프로그램은 운영 체제의 지역화 된 언어와 다른 언어의 기본 시스템 글꼴을 자동으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="05564-108">응용 프로그램이 실행 되 면 운영 체제에서 선택한 문화권에 맞는 글꼴이 자동으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05564-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="05564-109">글꼴을 설정 하는 것이 아니라 글꼴 스타일을 변경 하는 경우에는 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="05564-110">사용자가 단추를 클릭 하 여 텍스트 상자의 텍스트를 굵게 표시 하는 응용 프로그램의 경우에는이 작업을 수행 하는 것이 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05564-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="05564-111">이렇게 하려면 폼의 글꼴이 무엇 인지에 따라 텍스트 상자의 글꼴 스타일을 굵게 변경 하는 함수를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="05564-112">단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기와 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 처리기의 두 위치에서이 함수를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="05564-113"><xref:System.Windows.Forms.Control.Click> 이벤트 처리기 에서만 함수를 호출 하 고 일부 코드 조각이 전체 폼의 글꼴 패밀리를 변경 하는 경우 텍스트 상자는 폼의 나머지 부분으로 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05564-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

<span data-ttu-id="05564-114">그러나 응용 프로그램을 지역화할 때 굵은 글꼴이 특정 언어에 대해 제대로 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05564-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="05564-115">이 경우 지역화 담당자에 게 글꼴을 굵게 전환 하 여 일반 텍스트로 전환 하는 옵션이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="05564-116">지역화 담당자는 일반적으로 개발자가 아니라 소스 코드에 대 한 액세스 권한이 없기 때문에 리소스 파일에이 옵션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="05564-117">이렇게 하려면 <xref:System.Drawing.Font.Bold%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="05564-118">그 결과, 지역화 담당자가 편집할 수 있는 리소스 파일에 글꼴 설정이 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05564-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="05564-119">그런 다음 `InitializeComponent` 메서드 뒤에 코드를 작성 하 여 폼의 글꼴이 무엇이 든, 리소스 파일에 지정 된 글꼴 스타일을 사용 하 여 글꼴을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05564-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="05564-120">참조</span><span class="sxs-lookup"><span data-stu-id="05564-120">See also</span></span>

- [<span data-ttu-id="05564-121">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="05564-121">Using Fonts and Text</span></span>](using-fonts-and-text.md)
