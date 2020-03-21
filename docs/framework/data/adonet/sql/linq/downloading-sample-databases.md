---
title: ADO.NET 코드 샘플에 대한 샘플 SQL Server 데이터베이스 받기
description: ADO.NET 설명서의 코드 샘플에 사용된 SQL Server 데이터베이스와 SQL Server 및 관리 도구 다운로드
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148389"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>ADO.NET 코드 샘플에 대한 샘플 데이터베이스 받기

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서의 여러 예제 및 연습에서는 샘플 SQL Server 데이터베이스 및 SQL Server Express를 사용합니다. 이러한 제품은 Microsoft에서 무료로 다운로드할 수 있습니다.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>SQL Server용 Northwind 샘플 데이터베이스 받기

다음 GitHub 리포지토리에서 스크립트를 `instnwnd.sql` 다운로드하여 SQL Server용 Northwind 샘플 데이터베이스를 만들고 로드합니다.

[마이크로소프트 SQL 서버에 대 한 노스 윈드 및 술집 샘플 데이터베이스](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Northwind 데이터베이스를 사용하려면 다운로드한 `instnwnd.sql` 스크립트 파일을 실행하여 SQL Server 관리 [스튜디오](#get_ssms) 또는 유사한 도구를 사용하여 SQL Server 인스턴스에서 데이터베이스를 다시 만들어야 합니다. 저장소의 Readme 파일의 지침을 따릅니다.

> [!TIP]
> Microsoft Access에 대한 노스윈드 데이터베이스를 찾고 있는 경우 [Microsoft Access에 대한 노스윈드 샘플 데이터베이스 설치를](#northwind_access)참조하십시오.

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a>마이크로 소프트 액세스에 대한 노스 윈드 샘플 데이터베이스 받기

Microsoft 액세스에 대한 노스윈드 샘플 데이터베이스는 Microsoft 다운로드 센터에서 사용할 수 없습니다. Access 내에서 직접 Northwind를 설치하려면 다음 작업을 수행합니다.

1. 오픈 액세스.

1. **온라인 템플릿 검색** 상자에 **Northwind를** 입력한 다음 **Enter**를 선택합니다.

1. 결과 화면에서 **노스윈드를**선택합니다. Northwind 데이터베이스에 대한 설명과 함께 새 창이 열립니다.

1. 새 창에서 파일 **이름** 텍스트 상자에 Northwind 데이터베이스 복사본에 대 한 파일 이름을 제공 합니다.

1. **만들기**를 선택합니다. Access는 Northwind 데이터베이스를 다운로드하고 파일을 준비합니다.

1. 이 프로세스가 완료되면 시작 화면으로 데이터베이스가 열립니다.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>SQL 서버에 대한 AdventureWorks 샘플 데이터베이스 받기

다음 GitHub 리포지토리에서 SQL Server용 AdventureWorks 샘플 데이터베이스를 다운로드합니다.

[AdventureWorks 예제 데이터베이스](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

데이터베이스 백업(.bak)\*파일 중 하나를 다운로드한 후 SSMS(SQL Server 관리 스튜디오)를 사용하여 SQL Server 인스턴스에 백업을 복원합니다. [SQL 서버 관리 스튜디오 받기를](#get_ssms)참조하십시오.

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a>SQL 서버 관리 스튜디오 받기
다운로드한 데이터베이스를 보거나 수정하려면 Sql Server 관리 스튜디오(SSMS)를 사용할 수 있습니다. 다음 페이지에서 SSMS를 다운로드합니다.

[SSMS(SQL Server Management Studio) 다운로드](/sql/ssms/download-sql-server-management-studio-ssms)

IDE(Visual Studio 통합 개발 환경)에서 데이터베이스를 보고 관리할 수도 있습니다. [Visual Studio에서](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)SQL Server **개체 탐색기에서**데이터베이스에 연결하거나 **서버 탐색기**의 데이터베이스에 대한 데이터 연결을 만듭니다. **보기** 메뉴에서 이러한 탐색기 창을 엽니다.

## <a name="get-sql-server-express"></a><a name="get_sql"></a>SQL 서버 익스프레스 받기

SQL Server Express는 응용 프로그램과 함께 재배포할 수 있는 무료 엔트리 레벨 버전의 SQL Server입니다. 다음 페이지에서 SQL Server 익스프레스 다운로드:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

[비주얼 스튜디오를](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)사용하는 경우 SQL Server Express LocalDB는 비주얼 스튜디오의 무료 커뮤니티 버전뿐만 아니라 전문 및 상위 버전에도 포함되어 있습니다.  

## <a name="see-also"></a>참고 항목

- [시작](getting-started.md)
