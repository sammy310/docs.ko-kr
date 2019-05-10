---
title: '연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 직렬화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: c8321f98b25026e32e7c69f7029f2c589d0567f7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211595"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="85612-102">연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 직렬화</span><span class="sxs-lookup"><span data-stu-id="85612-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="85612-103">사용자 지정 컨트롤 노출 하는 속성으로 컬렉션 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85612-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="85612-104">이 연습을 사용 하는 방법에 설명 합니다 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 디자인 타임에 컬렉션 serialize 되는 방식을 제어 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="85612-105">적용 된 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 컬렉션 속성에 값을 입력 하면 속성을 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="85612-106">이 항목의 코드를 단일 목록으로 복사하려면 [방법: Designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 serialize](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="85612-107">전제 조건</span><span class="sxs-lookup"><span data-stu-id="85612-107">Prerequisites</span></span>

<span data-ttu-id="85612-108">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="85612-109">직렬화 가능 컬렉션을 사용 하 여 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="85612-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="85612-110">첫 번째 단계는 컨트롤 속성으로 직렬화 가능 컬렉션을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="85612-111">사용 하 여이 컬렉션의 콘텐츠를 편집할 수 있습니다 합니다 **컬렉션 편집기**에서 액세스할 수 있는 합니다 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="85612-112">Visual Studio에서 라는 Windows 컨트롤 라이브러리 프로젝트를 만들 `SerializationDemoControlLib`합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-112">In Visual Studio, create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="85612-113">자세한 내용은 [Windows 컨트롤 라이브러리 템플릿을](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-113">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="85612-114">이름 바꾸기 `UserControl1` 에 `SerializationDemoControl`입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-114">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="85612-115">자세한 내용은 [이름 바꾸기 리팩터링 코드 기호](/visualstudio/ide/reference/rename)합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-115">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="85612-116">에 **속성** 창에서 값을 설정 합니다 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> 속성을 `10`입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-116">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="85612-117">위치는 <xref:System.Windows.Forms.TextBox> 에서 제어를 `SerializationDemoControl`입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-117">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="85612-118"><xref:System.Windows.Forms.TextBox> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-118">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="85612-119">에 **속성** 창에서 다음 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-119">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="85612-120">속성</span><span class="sxs-lookup"><span data-stu-id="85612-120">Property</span></span>|<span data-ttu-id="85612-121">다음으로 변경</span><span class="sxs-lookup"><span data-stu-id="85612-121">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="85612-122">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="85612-122">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="85612-123">**도킹**</span><span class="sxs-lookup"><span data-stu-id="85612-123">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="85612-124">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="85612-124">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="85612-125">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="85612-125">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="85612-126">에 **코드 편집기**, 명명 된 문자열 배열 필드를 선언 `stringsValue` 에서 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-126">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="85612-127">정의 된 `Strings` 속성에는 `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="85612-127">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="85612-128"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> 값 컬렉션의 serialization을 사용 하도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85612-128">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="85612-129">키를 눌러 **F5** 프로젝트를 빌드하고에서 컨트롤을 실행 하는 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-129">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="85612-130">찾을 합니다 `Strings` 속성에는 <xref:System.Windows.Forms.PropertyGrid> 의 **UserControl 테스트 컨테이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-130">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="85612-131">클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭 하는 **문자열 컬렉션 편집기**.</span><span class="sxs-lookup"><span data-stu-id="85612-131">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="85612-132">여러 문자열을 입력 합니다 **문자열 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-132">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="85612-133">키를 눌러 구별 합니다 **Enter** 각 문자열의 끝에 키입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-133">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="85612-134">클릭 **확인** 문자열 입력이 완료 되 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-134">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="85612-135">입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-135">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="85612-136">컬렉션 속성을 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="85612-136">Serializing a Collection Property</span></span>

<span data-ttu-id="85612-137">컨트롤의 serialization 동작을 테스트 하려면 폼에 배치할을 사용 하 여 컬렉션의 콘텐츠를 변경 합니다 **컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-137">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="85612-138">특수 한 디자이너 파일을 보면 serialized 컬렉션 상태를 확인할 수는 **Windows Forms 디자이너** 에서 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-138">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="85612-139">컬렉션 serialize</span><span class="sxs-lookup"><span data-stu-id="85612-139">To serialize a collection</span></span>

1. <span data-ttu-id="85612-140">Windows 응용 프로그램 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-140">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="85612-141">프로젝트 이름을 `SerializationDemoControlTest`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-141">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="85612-142">에 **도구 상자**, 라는 탭을 찾으려면 **SerializationDemoControlLib 구성 요소**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-142">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="85612-143">이 탭에서 찾을 수 있습니다는 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-143">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="85612-144">자세한 내용은 [연습: 사용자 지정 구성 요소를 사용 하 여 도구 상자에 자동으로 채우기](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-144">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="85612-145">위치는 `SerializationDemoControl` 양식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-145">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="85612-146">찾을 합니다 `Strings` 속성에는 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-146">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="85612-147">클릭는 `Strings` 속성을 다음 줄임표 (![VisualStudioEllipsesButton 스크린 샷](../media/vbellipsesbutton.png "vbEllipsesButton")) 버튼을 클릭 하는 **문자열 컬렉션 편집기**.</span><span class="sxs-lookup"><span data-stu-id="85612-147">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="85612-148">여러 문자열을 입력 합니다 **문자열 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-148">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="85612-149">각 문자열의 끝에서 ENTER 키를 눌러 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-149">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="85612-150">클릭 **확인** 문자열 입력이 완료 되 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-150">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="85612-151">입력 문자열에 표시 된 <xref:System.Windows.Forms.TextBox> 의 `SerializationDemoControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-151">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="85612-152">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-152">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="85612-153">엽니다는 **Form1** 노드.</span><span class="sxs-lookup"><span data-stu-id="85612-153">Open the **Form1** node.</span></span> <span data-ttu-id="85612-154">아래 호출 파일 이기 **Form1.Designer.cs** 하거나 **Form1.Designer.vb**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-154">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="85612-155">이 파일은 파일에는 **Windows Forms 디자이너** 폼과 해당 자식 컨트롤의 디자인 타임 상태를 나타내는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="85612-155">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="85612-156">**코드 편집기**에서 이 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85612-156">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="85612-157">라는 영역을 엽니다 **Windows Form 디자이너에서 코드 생성** 레이블이 지정 된 섹션을 찾습니다 **serializationDemoControl1**합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-157">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="85612-158">이 레이블 아래에 있는 컨트롤의 serialize 된 상태를 나타내는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-158">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="85612-159">5 단계에서 입력 문자열에 대 한 할당에 표시 된 `Strings` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-159">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="85612-160">C# 및 Visual Basic의 경우 다음 코드 예제에서는 볼 수 있는 것은 문자열 "red", "주황색" 및 "노란색"를 입력 하는 경우 비슷한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85612-160">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="85612-161">에 **코드 편집기**의 값을 변경 합니다 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> 에 `Strings` 속성을 <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="85612-161">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="85612-162">3-4 단계를 반복 고 솔루션을 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-162">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="85612-163">이 경우에 **Windows Forms 디자이너** 대 한 할당이 내보냅니다는 `Strings` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="85612-163">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="85612-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="85612-164">Next Steps</span></span>

<span data-ttu-id="85612-165">표준 형식의 컬렉션을 직렬화 하는 방법을 알고, 디자인 타임 환경에 사용자 지정 컨트롤을 보다 강력 하 게 통합 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="85612-165">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="85612-166">다음 항목에는 사용자 지정 컨트롤의 디자인 타임 통합을 개선 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="85612-166">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="85612-167">[디자인 타임 아키텍처](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="85612-167">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="85612-168">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="85612-168">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="85612-169">[디자이너 Serialization 개요](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="85612-169">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="85612-170">연습: Visual Studio 디자인 타임 기능을 활용 하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="85612-170">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="85612-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="85612-171">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="85612-172">[디자이너 Serialization 개요](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="85612-172">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="85612-173">[방법: Designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 serialize](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="85612-173">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="85612-174">연습: 사용자 지정 구성 요소를 사용 하 여 도구 상자에 자동으로 채우기</span><span class="sxs-lookup"><span data-stu-id="85612-174">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
