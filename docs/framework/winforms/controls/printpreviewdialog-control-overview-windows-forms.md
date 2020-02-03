---
title: PrintPreviewDialog 컨트롤 개요
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741415"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="4932c-102">PrintPreviewDialog 컨트롤 개요 (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4932c-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="4932c-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 인쇄 시 [PrintDocument](printdocument-component-windows-forms.md) 표시 되는 방식을 표시 하는 데 사용 되는 미리 구성 된 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="4932c-104">사용자 고유의 대화 상자를 구성 하는 대신 Windows 기반 응용 프로그램 내에서 간단한 솔루션으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="4932c-105">컨트롤에는 인쇄, 확대, 한 페이지 또는 여러 페이지 표시 및 대화 상자 닫기 단추가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="4932c-106">키 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="4932c-106">Key properties and methods</span></span>

<span data-ttu-id="4932c-107">컨트롤의 키 속성은 미리 볼 문서를 설정 하는 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="4932c-108">문서는 <xref:System.Drawing.Printing.PrintDocument> 개체 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="4932c-109">대화 상자를 표시 하려면 <xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="4932c-110">앤티앨리어싱을 사용 하면 텍스트가 더 부드럽게 표시 될 수 있지만 더 느리게 표시 될 수도 있습니다. 이를 사용 하려면 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="4932c-111">특정 속성은 <xref:System.Windows.Forms.PrintPreviewDialog> 포함 된 <xref:System.Windows.Forms.PrintPreviewControl>를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="4932c-112">이 <xref:System.Windows.Forms.PrintPreviewControl> 폼에 추가할 필요는 없습니다. 폼에 대화 상자를 추가할 때 <xref:System.Windows.Forms.PrintPreviewDialog>에 자동으로 포함 됩니다. <xref:System.Windows.Forms.PrintPreviewControl>를 통해 사용할 수 있는 속성의 예로는 컨트롤에서 가로 및 세로로 표시 되는 페이지 수를 결정 하는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="4932c-113"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 속성은 Visual Basic, 시각적 개체 C#`printPreviewDialog1.PrintPreviewControl.Columns` 또는 시각적 개체 C++`printPreviewDialog1->PrintPreviewControl->Columns`에서 `PrintPreviewDialog1.PrintPreviewControl.Columns`으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="4932c-114">PrintPreviewDialog 성능</span><span class="sxs-lookup"><span data-stu-id="4932c-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="4932c-115">다음 조건에서는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 매우 느리게 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="4932c-116">네트워크 프린터가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-116">A network printer is used.</span></span>
- <span data-ttu-id="4932c-117">이 프린터에 대 한 사용자 기본 설정 (예: 이중 설정)이 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="4932c-118">.NET Framework 4.5.2에서 실행 되는 앱의 경우 구성 파일의 \<appSettings > 섹션에 다음 키를 추가 하 여 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤 초기화의 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="4932c-119">`EnablePrintPreviewOptimization` 키가 다른 값으로 설정 된 경우 또는 키가 없는 경우 최적화가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="4932c-120">.NET Framework 4.6 이상 버전에서 실행 되는 앱의 경우, 앱 구성 파일의 [\<runtime >](../../configure-apps/file-schema/runtime/index.md) 섹션에서 [\<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에 다음 스위치를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="4932c-121">스위치가 없거나 다른 값으로 설정 된 경우에는 최적화가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="4932c-122"><xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> 이벤트를 사용 하 여 프린터 설정을 수정 하는 경우 최적화 구성 스위치를 설정한 경우에도 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 성능이 향상 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4932c-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="4932c-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4932c-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="4932c-124">PrintPreviewControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4932c-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="4932c-125">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4932c-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="4932c-126">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4932c-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
