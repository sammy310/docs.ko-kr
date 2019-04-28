---
title: '방법: 분석 힌트를 사용하여 잉크 분석'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: a4c38ddf52e9054fe9126df4b7e172548617b90d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777002"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="3c2c7-102">방법: 분석 힌트를 사용하여 잉크 분석</span><span class="sxs-lookup"><span data-stu-id="3c2c7-102">How to: Analyze Ink with Analysis Hints</span></span>
<span data-ttu-id="3c2c7-103">[System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) 에 대 한 힌트를 제공 합니다 [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-103">An [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) provides a hint for the [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) to which it is attached.</span></span>  <span data-ttu-id="3c2c7-104">힌트에서 지정한 영역에 적용 됩니다는 [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) 의 속성을 [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) 잉크 분석기를 추가 컨텍스트를 제공 하 고 인식 정확도 향상 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) property of the [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="3c2c7-105">합니다 [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) 힌트 영역 내에서 가져온 잉크를 분석 하는 경우이 컨텍스트 정보에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-105">The [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c2c7-106">예제</span><span class="sxs-lookup"><span data-stu-id="3c2c7-106">Example</span></span>  
 <span data-ttu-id="3c2c7-107">다음 예제는 여러를 사용 하는 응용 프로그램 [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) 양식에서 잉크 입력을 허용 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objects on a form that accepts ink input.</span></span> <span data-ttu-id="3c2c7-108">응용 프로그램을 사용 합니다 [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) 양식의 각 항목에 대 한 컨텍스트 정보를 제공 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="3c2c7-109">응용 프로그램 백그라운드 분석을 사용 하 여 잉크를 분석 하 고 형식의 모든 잉크 사용자 잉크 추가 중지 한 후에 5 초를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="3c2c7-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
