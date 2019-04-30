---
title: LINQ to SQL 원본 코드 분석
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 2d8c5a89cbf09ef3829669a3d5272f742fa6582c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033854"
---
# <a name="analyzing-linq-to-sql-source-code"></a>LINQ to SQL 원본 코드 분석
다음 단계에 따라 Northwind 샘플 데이터베이스에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 소스 코드를 생성할 수 있습니다. 개체 모델 요소와 데이터베이스 요소를 비교하여 다른 항목이 매핑되는 방법을 보다 명확하게 볼 수 있습니다.  
  
> [!NOTE]
>  Visual Studio를 사용 하 여 개발자가 사용할 수는 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 이 코드를 생성 합니다.  
  
1. Northwind 샘플 데이터베이스가 개발 컴퓨터에 없는 경우 무료로 다운로드할 수 있습니다. 자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.  
  
2. Visual Basic 또는 C# 소스 파일을 생성하려면 SqlMetal 명령줄 도구를 사용합니다. 자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요. 명령 프롬프트에 다음 명령을 입력하여 저장 프로시저 및 함수를 포함하는 Visual Basic 및 C# 소스 파일을 생성할 수 있습니다.  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a>참고자료

- [참조](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [배경 정보](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
