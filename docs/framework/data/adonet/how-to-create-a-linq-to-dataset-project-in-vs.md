---
title: LINQ to DataSet 프로젝트 Visual Studio에서 만들기
ms.date: 08/15/2018
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
ms.openlocfilehash: 22763d3b9581d09d7bdda0c09480f8d36bb8e2ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667051"
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>방법: LINQ to DataSet 프로젝트 Visual Studio에서 만들기

다양 한 LINQ 프로젝트에 필요한 특정 어셈블리 참조 및 가져온된 네임 스페이스 (Visual Basic) 또는 [를 사용 하 여](../../../csharp/language-reference/keywords/using-directive.md) 지시문 (C#). LINQ에 대 한 최소 요구 사항에 대 한 참조는 *System.Core.dll* 와 `using` 에 대 한 지시문 <xref:System.Linq>합니다.

이러한 요구 사항은 Visual Studio 2017에서 새 C# 콘솔 앱 프로젝트를 만드는 경우 기본적으로 제공 됩니다. 이전 버전의 Visual Studio에서 프로젝트를 업그레이드 하는 경우 이러한 LINQ 관련 참조를 수동으로 제공 해야 합니다.

LINQ to DataSet에 대 한 두 개의 추가 참조가 필요 *System.Data.dll* 하 고 *System.Data.DataSetExtensions.dll*합니다.

> [!NOTE]
> LINQ 관련 Dll을 명령 프롬프트에서 빌드하는 경우 직접 참조 해야 합니다 *%ProgramFiles%\Reference Assemblies\Microsoft\Framework\v3.5*합니다.

## <a name="to-enable-linq-to-dataset-functionality"></a>LINQ to DataSet 기능을 사용하려면

LINQ to DataSet 기능 기존 프로젝트에서 사용 하도록 설정 하려면 다음이 단계를 수행 합니다.

1. 에 대 한 참조를 추가 **System.Core**를 **System.Data**, 및 **System.Data.DataSetExtensions**합니다.

   **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **참조** 노드와 선택 **참조 추가**합니다. 에 **참조 관리자** 대화 상자에서 **System.Core**에 **System.Data**, 및 **System.Data.DataSetExtensions**합니다. **확인**을 선택합니다.

1. 추가 [를 사용 하 여](../../../csharp/language-reference/keywords/using-directive.md) 지시문 (또는 [Imports 문](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Visual basic에서)에 대 한 **System.Data** 고 **System.Linq**합니다.

   ```csharp
   using System.Data;
   using System.Linq;
   ```

1. 필요에 따라 추가 `using` 지시문 (또는 `Imports` 문)에 대 한 **System.Data.Common** 하거나 **System.Data.SqlClient**데이터베이스에 연결 하는 방법에 따라 합니다.

## <a name="see-also"></a>참고 항목

- [LINQ to DataSet 사용 하 여 시작](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
