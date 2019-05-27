---
title: PrintPreviewDialog 컨트롤 개요(Windows Forms)
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dce6bf9cb9872183e60e6ccdf7eaf79b6630db51
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053691"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="0892f-102">PrintPreviewDialog 컨트롤 개요 (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0892f-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="0892f-103">Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 미리 구성 된 대화 상자를 표시 하는 데 사용 하는 방법을 [PrintDocument](printdocument-component-windows-forms.md) 인쇄할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="0892f-104">고유한 대화 상자를 구성 하는 대신 간단한 솔루션으로 Windows 기반 응용 프로그램 내에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="0892f-105">컨트롤에는 인쇄, 확대, 한 페이지 또는 여러 페이지 표시 및 대화 상자 닫기 단추가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="0892f-106">키 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="0892f-106">Key properties and methods</span></span>

<span data-ttu-id="0892f-107">컨트롤의 키 속성은 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>를 설정 하는 문서를 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="0892f-108">해당 문서를 <xref:System.Drawing.Printing.PrintDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="0892f-109">대화 상자를 표시 하기 위해 호출 해야 해당 <xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="0892f-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="0892f-110">앤티 앨리어싱을 매끄럽게, 표시 텍스트를 만들 수 있지만 느린; 표시도 가능 를 사용 하려면 다음을 설정 합니다 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="0892f-111">특정 속성을 통해 사용할 수는 <xref:System.Windows.Forms.PrintPreviewControl> 는 <xref:System.Windows.Forms.PrintPreviewDialog> 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="0892f-112">(이 추가할 필요가 없습니다 <xref:System.Windows.Forms.PrintPreviewControl> ; 형식으로 자동으로 포함 된는 <xref:System.Windows.Forms.PrintPreviewDialog> 폼에 대화 상자를 추가 하면 됩니다.) 통해 사용할 수 있는 속성의 예는 <xref:System.Windows.Forms.PrintPreviewControl> 는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 가로 및 세로로 컨트롤에 표시 되는 페이지 수를 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="0892f-113">액세스할 수 있습니다 합니다 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 속성으로 `PrintPreviewDialog1.PrintPreviewControl.Columns` Visual basic에서는 `printPreviewDialog1.PrintPreviewControl.Columns` 시각적 개체의 C#, 또는 `printPreviewDialog1->PrintPreviewControl->Columns` 시각적 개체에 C++.</span><span class="sxs-lookup"><span data-stu-id="0892f-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="0892f-114">PrintPreviewDialog 성능</span><span class="sxs-lookup"><span data-stu-id="0892f-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="0892f-115">다음과 같은 경우에 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤 매우 느리게 초기화:</span><span class="sxs-lookup"><span data-stu-id="0892f-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="0892f-116">네트워크 프린터 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-116">A network printer is used.</span></span>
- <span data-ttu-id="0892f-117">양면 인쇄 설정 등이 프린터에 대 한 사용자 기본 설정은 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="0892f-118">.NET Framework 4.5.2에서 실행 되는 앱에 대 한 다음 키를 추가할 수 있습니다 합니다 \<appSettings >의 성능 향상을 위해 구성 파일의 섹션 <xref:System.Windows.Forms.PrintPreviewDialog> 초기화를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="0892f-119">경우는 `EnablePrintPreviewOptimization` 키가 다른 값으로 설정 하거나 키가 있는 경우 최적화를 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="0892f-120">.NET Framework 4.6 이상 버전에서 실행 되는 앱에 다음 스위치를 추가할 수 있습니다 합니다 [ \<AppContextSwitchOverrides >](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 요소에는 [ \<런타임 >](../../configure-apps/file-schema/runtime/index.md) 앱 구성 파일의 섹션:</span><span class="sxs-lookup"><span data-stu-id="0892f-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="0892f-121">스위치가 있는 경우 또는 다른 값으로 설정 된 경우 최적화를 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="0892f-122">사용 하는 경우는 <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> 성능을 프린터 설정을 수정 하려면 이벤트를 <xref:System.Windows.Forms.PrintPreviewDialog> 최적화 구성 스위치를 설정한 경우에 제어 향상 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0892f-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="0892f-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="0892f-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="0892f-124">PrintPreviewControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0892f-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="0892f-125">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0892f-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="0892f-126">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0892f-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
