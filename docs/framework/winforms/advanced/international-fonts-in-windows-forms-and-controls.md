---
title: Windows Forms 및 컨트롤에서 국가별 글꼴
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
ms.openlocfilehash: 1f9afd575e2de04e0b11556ad34436839e13d968
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942898"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a><span data-ttu-id="d9e50-102">Windows Forms 및 컨트롤에서 국가별 글꼴</span><span class="sxs-lookup"><span data-stu-id="d9e50-102">International fonts in Windows Forms and controls</span></span>

<span data-ttu-id="d9e50-103">국가별 응용 프로그램에서 글꼴을 선택 하는 권장된 방법은 가능한 글꼴 대체 (fallback)를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-103">In International applications, the recommended method of selecting fonts is to use font fallback wherever possible.</span></span> <span data-ttu-id="d9e50-104">시스템 문자 스크립트 내용을 확인 하는 글꼴 대체 수단에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-104">Font fallback means that the system determines what script the character belongs to.</span></span>

## <a name="using-font-fallback"></a><span data-ttu-id="d9e50-105">글꼴 대체 (fallback)를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d9e50-105">Using font fallback</span></span>

<span data-ttu-id="d9e50-106">이 기능을 이용 하려면 설정 하지는 <xref:System.Drawing.Font> 폼 또는 다른 요소에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-106">To take advantage of this feature, don't set the <xref:System.Drawing.Font> property for your form or any other element.</span></span> <span data-ttu-id="d9e50-107">응용 프로그램에는 다른 운영 체제의 지역화 된 언어에서 다른 기본 시스템 글꼴을 자동으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-107">The application will automatically use the default system font, which differs from one localized language of the operating system to another.</span></span> <span data-ttu-id="d9e50-108">응용 프로그램을 실행 하면 시스템 운영 체제에서 선택한 문화권에 대 한 올바른 글꼴을 자동으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-108">When the application runs, the system will automatically provide the correct font for the culture selected in the operating system.</span></span>

<span data-ttu-id="d9e50-109">글꼴 스타일을 변경 하는 것에 대 한 인 글꼴을 설정 하지 않는 규칙에 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-109">There's an exception to the rule of not setting the font, which is for changing the font style.</span></span> <span data-ttu-id="d9e50-110">이는 사용자가 굵게 표시 된에서 텍스트 상자에 텍스트를 표시 하려면 단추를 클릭 하는 응용 프로그램에 대해 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-110">This might be important for an application in which the user clicks a button to make text in a text box appear in boldface.</span></span> <span data-ttu-id="d9e50-111">이렇게 하려면 하는 함수를 작성 굵게, 텍스트 상자의 글꼴 스타일을 변경 하려면 폼의 글꼴에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-111">To do that, you would write a function to change the text box's font style to bold, based on whatever the form's font is.</span></span> <span data-ttu-id="d9e50-112">두 위치에서이 함수를 호출 하는 것이 반드시: 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및는 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-112">It's important to call this function in two places: in the button's <xref:System.Windows.Forms.Control.Click> event handler and in the <xref:System.Windows.Forms.Control.FontChanged> event handler.</span></span> <span data-ttu-id="d9e50-113">에서만 함수를 호출 하는 경우는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및 코드의 다른 일부 전체 폼의 글꼴 패밀리를 변경, 텍스트 상자 폼의 나머지 부분을 사용 하 여 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-113">If the function is called only in the <xref:System.Windows.Forms.Control.Click> event handler and some other piece of code changes the font family of the entire form, the text box doesn't change with the rest of the form.</span></span>

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

<span data-ttu-id="d9e50-114">그러나 응용 프로그램을 지역화할 때 굵게 표시할 수 있습니다 특정 잘못 언어.</span><span class="sxs-lookup"><span data-stu-id="d9e50-114">However, when you localize your application, the bold font may display poorly for certain languages.</span></span> <span data-ttu-id="d9e50-115">중요 한 경우 일반 텍스트를 굵은 글꼴 전환 옵션이 지역화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-115">If this is a concern, you want the localizers to have the option of switching the font from bold to regular text.</span></span> <span data-ttu-id="d9e50-116">하므로 지역화 담당자는 일반적으로 개발자가 아닌 및 소스 코드에 액세스할 수 없는, 리소스 파일에만이 옵션 해야 리소스 파일에서 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-116">Since localizers are typically not developers and don't have access to source code, only to resource files, this option needs to be set in the resource files.</span></span> <span data-ttu-id="d9e50-117">이 위해 설정 된 <xref:System.Drawing.Font.Bold%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-117">To do this, you would set the <xref:System.Drawing.Font.Bold%2A> property to `true`.</span></span> <span data-ttu-id="d9e50-118">따라서 지역화 담당자가 편집할 수 있는 리소스 파일에 작성 되 고 글꼴 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-118">This results in the font setting being written out to the resource files, where localizers can edit it.</span></span> <span data-ttu-id="d9e50-119">그런 다음 후 코드를 작성 하는 `InitializeComponent` 글꼴을 다시 설정 하는 방법에 따라 폼의 글꼴, 하지만 리소스 파일에 지정 된 글꼴 스타일을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e50-119">You then write code after the `InitializeComponent` method to reset the font based on whatever the form's font is, but using the font style specified in the resource file.</span></span>

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a><span data-ttu-id="d9e50-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="d9e50-120">See also</span></span>

- [<span data-ttu-id="d9e50-121">Windows Forms 응용 프로그램 전역화</span><span class="sxs-lookup"><span data-stu-id="d9e50-121">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
- [<span data-ttu-id="d9e50-122">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="d9e50-122">Using Fonts and Text</span></span>](using-fonts-and-text.md)
