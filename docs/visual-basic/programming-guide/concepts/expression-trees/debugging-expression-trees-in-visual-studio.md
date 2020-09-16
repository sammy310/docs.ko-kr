---
title: Visual Studio에서 식 트리 디버그
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: a256ef852a446a189451632c87598b04c374f884
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551121"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Visual Studio에서 식 트리 디버깅 (Visual Basic)
애플리케이션을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다. 식 트리 구조에 대한 간략한 개요를 보려면 [특수 구문](debugview-syntax.md)을 사용하여 식 트리를 나타내는 `DebugView` 속성을 사용합니다. (`DebugView`는 디버그 모드에서만 사용할 수 있습니다.)  

![식 트리의 DebugView의 스크린샷](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

`DebugView`는 문자열이므로 `DebugView` 레이블 옆의 돋보기 아이콘에서 **텍스트 시각화 도우미**를 선택하여 [기본 제공 텍스트 시각화 도우미](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)를 사용하여 여러 줄에서 볼 수 있습니다.

 ![DebugView의 결과에 적용 된 텍스트 시각화 도우미의 스크린샷](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

또는 다음과 같은 식 트리에 [사용자 지정 시각화 도우미](/visualstudio/debugger/create-custom-visualizers-of-data)를 설치하여 사용할 수 있습니다.

- [읽을 수 있는 식](https://github.com/agileobjects/ReadableExpressions)([MIT 라이선스](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)에서 사용 가능)은 다양한 렌더링 옵션을 사용하여 식 트리를 테마 지정 가능 C# 코드로 렌더링합니다.

  ![읽을 수 있는 식 시각화 도우미의 스크린샷](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [식 트리 시각화 도우미](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT 라이선스](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE))는 식 트리 및 해당 개별 노드의 트리 뷰를 제공 합니다. 및는 Visual Basic 구문을 사용 하 여 식 트리를 렌더링할 수 있습니다.

  ![식 트리 시각화 도우미의 스크린샷](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>식 트리에 대한 시각화 도우미를 열려면  
  
1. **DataTips**, **조사식** 창, **자동** 창 또는 **지역** 창의 식 트리 옆에 나타나는 돋보기 아이콘을 클릭합니다.  
  
    사용 가능한 시각화 도우미의 목록이 나타납니다.

    ![Visual Studio에서 시각화 도우미가 열리는 사용자의 스크린샷](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. 사용할 시각화 도우미를 클릭합니다.  

## <a name="see-also"></a>참조

- [식 트리(Visual Basic)](index.md)
- [Visual Studio의 디버깅](/visualstudio/debugger/debugger-feature-tour)
- [Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)
- [`DebugView` 구문](debugview-syntax.md)
