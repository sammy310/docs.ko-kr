---
title: 폼 크기 조정
description: Size 속성의 새 값을 설정 하 여 폼의 높이와 너비를 모두 조정 하거나 높이 또는 너비 속성을 개별적으로 조정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 0d6383e4d29d9407d3da97bf8b94761f06d99748
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903274"
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="a35c1-103">방법: Windows Forms 크기 조정</span><span class="sxs-lookup"><span data-stu-id="a35c1-103">How to: Resize Windows Forms</span></span>

<span data-ttu-id="a35c1-104">여러가지 방법으로 Windows Form의 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-104">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="a35c1-105"><xref:System.Windows.Forms.Form.Size%2A> 속성에 대해 새 값을 설정하거나 <xref:System.Windows.Forms.Control.Height%2A> 또는 <xref:System.Windows.Forms.Control.Width%2A> 속성을 개별적으로 조정하여 프로그래밍 방식으로 폼의 높이와 너비를 모두 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-105">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="a35c1-106">Visual Studio를 사용 하는 경우 Windows Forms 디자이너를 사용 하 여 크기를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-106">If you're using Visual Studio, you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="a35c1-107">또한 [방법: 디자이너를 사용 하 여 Windows Forms 크기 조정을](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a35c1-107">Also see [How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).</span></span>

## <a name="resize-a-form-programmatically"></a><span data-ttu-id="a35c1-108">프로그래밍 방식으로 폼 크기 조정</span><span class="sxs-lookup"><span data-stu-id="a35c1-108">Resize a form programmatically</span></span>

<span data-ttu-id="a35c1-109">폼의 <xref:System.Windows.Forms.Form.Size%2A> 속성을 설정하여 런타임에 폼의 크기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-109">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>

<span data-ttu-id="a35c1-110">다음 코드 예제에서는 100 × 100 픽셀로 설정된 폼 크기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-110">The following code example shows the form size set to 100 × 100 pixels.</span></span>

```vb
Form1.Size = New System.Drawing.Size(100, 100)
```

```csharp
Form1.Size = new System.Drawing.Size(100, 100);
```

```cpp
Form1->Size = System::Drawing::Size(100, 100);
```

## <a name="change-form-width-and-height-programmatically"></a><span data-ttu-id="a35c1-111">프로그래밍 방식으로 폼 너비 및 높이 변경</span><span class="sxs-lookup"><span data-stu-id="a35c1-111">Change form width and height programmatically</span></span>

<span data-ttu-id="a35c1-112"><xref:System.Windows.Forms.Form.Size%2A>가 정의된 후 <xref:System.Windows.Forms.Control.Width%2A> 또는 <xref:System.Windows.Forms.Control.Height%2A> 속성을 사용하여 폼 높이나 너비를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-112">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>

<span data-ttu-id="a35c1-113">다음 코드 예제에서는 높이가 일정하게 유지되고 폼의 왼쪽 가장자리에서 300픽셀로 설정된 폼의 너비를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-113">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>

```vb
Form1.Width = 300
```

```csharp
Form1.Width = 300;
```

```cpp
Form1->Width = 300;
```

<span data-ttu-id="a35c1-114">또는</span><span class="sxs-lookup"><span data-stu-id="a35c1-114">-or-</span></span>

<span data-ttu-id="a35c1-115"><xref:System.Windows.Forms.Form.Size%2A> 속성을 설정하여 <xref:System.Drawing.Size.Width%2A> 또는 <xref:System.Drawing.Size.Height%2A>를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-115">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>

<span data-ttu-id="a35c1-116">그러나 다음 코드 예제와 같이 이 접근 방식은 단순히 <xref:System.Windows.Forms.Control.Width%2A> 또는 <xref:System.Windows.Forms.Control.Height%2A> 속성을 설정하는 것보다 성가십니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-116">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>

```vb
Form1.Size = New Size(300, Form1.Size.Height)
```

```csharp
Form1.Size = new Size(300, Form1.Size.Height);
```

```cpp
Form1->Size = System::Drawing::Size(300, Form1->Size.Height);
```

## <a name="change-form-size-by-increments-programmatically"></a><span data-ttu-id="a35c1-117">프로그래밍 방식으로 증가 하 여 폼 크기 변경</span><span class="sxs-lookup"><span data-stu-id="a35c1-117">Change form size by increments programmatically</span></span>

<span data-ttu-id="a35c1-118">폼의 크기를 증가시키려면 <xref:System.Drawing.Size.Width%2A> 및 <xref:System.Drawing.Size.Height%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-118">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>

<span data-ttu-id="a35c1-119">다음 코드 예제에서는 현재 설정보다 200픽셀 넓게 설정된 폼의 너비를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-119">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>

```vb
Form1.Width += 200
```

```csharp
Form1.Width += 200;
```

```cpp
Form1->Width += 200;
```

> [!CAUTION]
> <span data-ttu-id="a35c1-120"><xref:System.Windows.Forms.Form.Size%2A> 속성을 새로운 <xref:System.Drawing.Size> 구조체로 설정하여 동시에 높이 및 너비 크기를 설정하지 않는 한 항상 <xref:System.Drawing.Size.Height%2A> 또는 <xref:System.Drawing.Size.Width%2A> 속성을 사용하여 폼의 크기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-120">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="a35c1-121"><xref:System.Windows.Forms.Form.Size%2A> 속성은 값 형식인 <xref:System.Drawing.Size> 구조체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-121">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="a35c1-122">값 형식의 속성에 새 값을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-122">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="a35c1-123">따라서 다음 코드 예제는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a35c1-123">Therefore, the following code example will not compile.</span></span>

```vb
' NOTE: CODE WILL NOT COMPILE
Dim f As New Form()
f.Size.Width += 100
```

```csharp
// NOTE: CODE WILL NOT COMPILE
Form f = new Form();
f.Size.Width += 100;
```

```cpp
// NOTE: CODE WILL NOT COMPILE
Form^ f = gcnew Form();
f->Size->X += 100;
```

## <a name="see-also"></a><span data-ttu-id="a35c1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a35c1-124">See also</span></span>

- [<span data-ttu-id="a35c1-125">Windows Forms 시작</span><span class="sxs-lookup"><span data-stu-id="a35c1-125">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
- [<span data-ttu-id="a35c1-126">Windows Forms 애플리케이션 강화</span><span class="sxs-lookup"><span data-stu-id="a35c1-126">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
