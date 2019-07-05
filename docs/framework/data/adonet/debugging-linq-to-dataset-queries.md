---
title: LINQ to DataSet 쿼리 디버깅
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: 38eda9f352c4a8d8590e5e57b48c694eadd0397b
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67503979"
---
# <a name="debugging-linq-to-dataset-queries"></a>LINQ to DataSet 쿼리 디버깅

Visual Studio 데이터 집합 코드를 LINQ의 디버깅을 지원 합니다. 그러나 차이가 일부 LINQ-LINQ가 아닌 관리 되는 데이터 집합 코드를 데이터 집합 코드를 디버깅 합니다. 대부분의 디버깅 기능은 LINQ를 사용 하 여 데이터 집합 문에, 단계별 실행, 중단점 설정 및 디버거 창에 표시 된 결과 보기를 포함 하 여 작동 합니다. 그러나 지연 된 쿼리 실행에서 LINQ 데이터 집합 코드를 디버깅 하는 동안 고려해 야 할 몇 가지 의도 있으며 편집 하며 계속 하기를 사용 하 여 몇 가지 제한이 있습니다. 이 항목에서는 LINQ to DataSet LINQ가 아닌 관리 되는 데이터 집합 코드에 비해에 고유한 디버깅 측면을 설명 합니다.  
  
## <a name="viewing-results"></a>결과 보기  
 DataTips, 조사식 창 및 간략 한 조사식 대화 상자를 사용 하 여 데이터 집합에는 LINQ의 결과 볼 수 있습니다. 소스 창을 사용할 때 소스 창의 쿼리 위에 포인터를 올려 놓으면 DataTips가 나타납니다. LINQ 데이터 집합 변수에 복사 하 여 조사식 창이 나 간략 한 조사식 대화 상자에 붙여 넣습니다. Linq to DataSet에서 쿼리를 실행 하는 경우에 있지만 만들어지거나 선언 될 때 쿼리 평가 되지 않습니다. 이 이라고 *지연 된 실행*합니다. 따라서 쿼리가 계산되기 전까지는 쿼리 변수에 값이 없습니다. 자세한 내용은 [LINQ to DataSet에서에서 쿼리](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)합니다.  
  
 쿼리 결과를 표시하려면 디버거에서 쿼리를 계산해야 합니다. 이러한 암시적 계산이 디버거에서 LINQ to DataSet 쿼리 결과 보기 및 것에 몇 가지 고려해 야 하는 경우 발생 합니다. 쿼리를 계산할 때마다 일정 시간이 소요됩니다. 결과 노드를 확장할 때 일정 시간이 소요됩니다. 일부 쿼리의 경우 계산을 반복하면 성능이 상당히 저하될 수 있습니다. 쿼리를 계산할 때 데이터의 값이나 프로그램의 상태가 변경되는 의도하지 않은 결과가 나타날 수 있습니다. 모든 쿼리에서 예기치 않은 결과가 나타나는 것은 아닙니다. 부작용 없이 쿼리를 안전 하 게 계산할 수 있는지를 확인 하려면 쿼리를 구현 하는 코드를 이해 해야 합니다. 자세한 내용은 [부작용 및 식](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120))합니다.  
  
## <a name="edit-and-continue"></a>편집하며 계속하기  
 편집 하며 계속 하기 변경 linq to DataSet 쿼리를 지원 하지 않습니다. 추가, 제거 또는 데이터 집합 문에 디버깅 세션 중 LINQ를 변경 하는 경우 변경 내용이 편집 하며 계속 하기에서 지원 되지 않습니다 알려 주는 대화 상자가 나타납니다. 이때 변경 내용을 취소할 수도 있고, 디버깅 세션을 중지하고 편집된 코드로 새 세션을 다시 시작할 수도 있습니다.  
  
 또한 편집 및 계속 형식 또는 데이터 집합에는 LINQ에서 사용 되는 변수 값을 변경할 수 없습니다. 이 경우에도 변경 내용을 취소할 수도 있고, 디버깅 세션을 중지하고 다시 시작할 수도 있습니다.  
  
 시각적 개체의 C# Visual Studio에서 사용할 수 없습니다 편집 하며 계속 하기는 LINQ to DataSet 쿼리에서 포함 하는 메서드에서 코드입니다.  
  
 Visual Studio에서 Visual basic에서 LINQ가 아닌 메서드는 LINQ to DataSet 쿼리에서 포함 하는 경우에 데이터 집합 코드에 편집 하며 계속 하기를 사용할 수 있습니다. 추가 하거나 LINQ to DataSet 쿼리에서의 줄 번호를 변경 하는 경우에 LINQ to DataSet 문 앞에 코드를 제거할 수 있습니다. 디버깅 환경은 LINQ가 아닌 데이터 집합 코드에 대 한 Visual Basic에서 LINQ to DataSet 도입 되기 전과 동일 합니다. 그러나 변경 하, 추가 또는 변경 내용을 적용 하려면 디버깅을 중지 하지 않는 한 LINQ to DataSet 쿼리에서 제거 수 없습니다.  
  
## <a name="see-also"></a>참고자료

- [관리 코드 디버그](/visualstudio/debugger/debugging-managed-code)
- [프로그래밍 가이드](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
