---
title: REF CURSOR 예제
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: b45ef971ccb6b785988cc351d02be9e0844f6e11
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200539"
---
# <a name="ref-cursor-examples"></a><span data-ttu-id="c572d-102">REF CURSOR 예제</span><span class="sxs-lookup"><span data-stu-id="c572d-102">REF CURSOR Examples</span></span>

<span data-ttu-id="c572d-103">REF CURSOR 예제는 REF CURSOR를 사용하는 다음 세 개의 Microsoft Visual Basic 예제로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-103">The REF CURSOR examples are comprised of the following three Microsoft Visual Basic examples that demonstrate using REF CURSORs.</span></span>  
  
|<span data-ttu-id="c572d-104">샘플</span><span class="sxs-lookup"><span data-stu-id="c572d-104">Sample</span></span>|<span data-ttu-id="c572d-105">Description</span><span class="sxs-lookup"><span data-stu-id="c572d-105">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c572d-106">OracleDataReader의 REF CURSOR 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c572d-106">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)|<span data-ttu-id="c572d-107">이 예제에서는 REF CURSOR 매개 변수를 반환하는 PL/SQL 저장 프로시저를 실행하고 값을 <xref:System.Data.OracleClient.OracleDataReader>로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-107">This example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>|  
|[<span data-ttu-id="c572d-108">OracleDataReader를 사용하여 여러 Multiple REF CURSOR에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="c572d-108">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)|<span data-ttu-id="c572d-109">이 예에서는 두 개의 REF CURSOR 매개 변수를 반환 하는 PL/SQL 저장 프로시저를 실행 하 고 **OracleDataReader**를 사용 하 여 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-109">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>|  
|[<span data-ttu-id="c572d-110">하나 이상의 REF CURSOR를 사용하여 데이터 세트 필터링</span><span class="sxs-lookup"><span data-stu-id="c572d-110">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)|<span data-ttu-id="c572d-111">이 예제에서는 두 개의 REF CURSOR 매개 변수를 반환하는 PL/SQL 저장 프로시저를 실행하고 반환되는 행으로 <xref:System.Data.DataSet>을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-111">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>|  
  
 <span data-ttu-id="c572d-112">이러한 예제를 사용하려면 Oracle 테이블을 만들거나 PL/SQL 패키지 및 패키지 본문을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-112">To use these examples, you may need to create the Oracle tables, and you must create a PL/SQL package and package body.</span></span>  
  
## <a name="creating-the-oracle-tables"></a><span data-ttu-id="c572d-113">Oracle 테이블 만들기</span><span class="sxs-lookup"><span data-stu-id="c572d-113">Creating the Oracle Tables</span></span>  

 <span data-ttu-id="c572d-114">이 예제에서는 Oracle Scott/Tiger 스키마에 정의된 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-114">These examples use tables that are defined in the Oracle Scott/Tiger schema.</span></span> <span data-ttu-id="c572d-115">Oracle Scott/Tiger 스키마는 대부분의 Oracle 설치와 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-115">The Oracle Scott/Tiger schema is included with most Oracle installations.</span></span> <span data-ttu-id="c572d-116">이 스키마가 없으면 {OracleHome}\rdbms\admin\scott.sql에 있는 SQL 명령 파일을 사용하여 이러한 예제에서 사용되는 테이블과 인덱스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-116">If this schema does not exist, you can use the SQL commands file in {OracleHome}\rdbms\admin\scott.sql to create the tables and indexes used by these examples.</span></span>  
  
## <a name="creating-the-oracle-package-and-package-body"></a><span data-ttu-id="c572d-117">Oracle 패키지 및 패키지 본문 만들기</span><span class="sxs-lookup"><span data-stu-id="c572d-117">Creating the Oracle Package and Package Body</span></span>  

 <span data-ttu-id="c572d-118">이러한 예제를 사용하려면 서버에 다음 PL/SQL 패키지 및 패키지 본문이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-118">These examples require the following PL/SQL package and package body on your server.</span></span> <span data-ttu-id="c572d-119">Oracle 서버에 다음 Oracle 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-119">Create the following Oracle package on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS
    TYPE T_CURSOR IS REF CURSOR;
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,
                               IO_CURSOR IN OUT T_CURSOR);
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/
```  
  
 <span data-ttu-id="c572d-120">Oracle 서버에 다음 Oracle 패키지 본문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c572d-120">Create the following Oracle package body on the Oracle server.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE BODY CURSPKG AS  
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,  
                               IO_CURSOR IN OUT T_CURSOR)  
    IS
        V_CURSOR T_CURSOR;
    BEGIN
        IF N_EMPNO <> 0
        THEN  
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO
                  AND EMP.EMPNO = N_EMPNO;  
  
        ELSE
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO;  
  
        END IF;  
        IO_CURSOR := V_CURSOR;
    END OPEN_ONE_CURSOR;
  
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,  
                                DEPTCURSOR OUT T_CURSOR)  
    IS
        V_CURSOR1 T_CURSOR;
        V_CURSOR2 T_CURSOR;
    BEGIN
        OPEN V_CURSOR1 FOR SELECT * FROM EMP;  
        OPEN V_CURSOR2 FOR SELECT * FROM DEPT;  
        EMPCURSOR  := V_CURSOR1;
        DEPTCURSOR := V_CURSOR2;
    END OPEN_TWO_CURSORS;
END CURSPKG;  
/  
```  
  
## <a name="see-also"></a><span data-ttu-id="c572d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c572d-121">See also</span></span>

- [<span data-ttu-id="c572d-122">Oracle REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="c572d-122">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)
- [<span data-ttu-id="c572d-123">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c572d-123">ADO.NET Overview</span></span>](ado-net-overview.md)
