---
title: Visual Studio (Visual Basic)에서 식 트리 디버깅
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 9aead09e0e9469f13e2d6befbad444d3c7fecabd
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196021"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Visual Studio (Visual Basic)에서 식 트리 디버깅
애플리케이션을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다. 식 트리 구조를 간단히 살펴보려면를 사용할 수 있습니다는 `DebugView` 속성을 나타내는 식 트리 [특수 구문을 사용 하 여](debugview-syntax.md)입니다. (`DebugView`는 디버그 모드에서만 사용할 수 있습니다.)  

![Visual Studio 디버거 내의 식 트리 DebugView](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

`DebugView`는 문자열이므로 `DebugView` 레이블 옆의 돋보기 아이콘에서 **텍스트 시각화 도우미**를 선택하여 [기본 제공 텍스트 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)를 사용하여 여러 줄에서 볼 수 있습니다.

 !['DebugView'의 결과에 적용되는 텍스트 시각화 도우미](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

설치 및 사용할 수는 한편 [사용자 지정 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) 식 트리에 대 한 같은:

* [읽을 수 있는 식](https://github.com/agileobjects/ReadableExpressions)([MIT 라이선스](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)에서 사용 가능)은 식 트리를 C# 코드로 렌더링합니다.

  ![읽을 수 있는 식 시각화 도우미](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [식 트리 시각화 도우미](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT 라이선스](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), 식 트리, 속성 및 관련된 개체의 그래픽 뷰를 제공 하 고 Visual Basic 코드를 사용 하 여 식 트리를 렌더링할 수 있습니다.

  ![ExpressionToString 시각화 도우미](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>식 트리에 대한 시각화 도우미를 열려면  
  
1. **DataTips**, **조사식** 창, **자동** 창 또는 **지역** 창의 식 트리 옆에 나타나는 돋보기 아이콘을 클릭합니다.  
  
     사용 가능한 시각화 도우미의 목록이 나타납니다. 

      ![Visual Studio에서 시각화 도우미 열기](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. 사용할 시각화 도우미를 클릭합니다.  

## <a name="see-also"></a>참고자료

- [식 트리(Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)
- [Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)
- [`DebugView` 구문](debugview-syntax.md)
