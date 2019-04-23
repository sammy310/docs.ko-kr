---
title: ASP.NET을 사용하는 LINQ to SQL N 계층
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 80c12d1c9f290657a6e005063d9cc77a17354abd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103735"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>ASP.NET을 사용하는 LINQ to SQL N 계층
[!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 을 사용하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]응용 프로그램에서는 <xref:System.Web.UI.WebControls.LinqDataSource> 웹 서버 컨트롤을 사용합니다. 이 컨트롤은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대해 쿼리하는 데 필요한 대부분의 논리를 처리하고, 데이터를 브라우저에 전달하고 검색하며, 최종적으로 데이터베이스를 업데이트할 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> 에 데이터를 제출합니다. 컨트롤을 태그에 구성하기만 하면 컨트롤이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 과 브라우저 사이의 모든 데이터 전송을 처리합니다. 프레젠테이션 계층과의 상호 작용은 이 컨트롤이 처리하고 데이터 계층과의 통신은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 이 처리하기 때문에 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 다계층 애플리케이션에서 사용자는 사용자 지정 비즈니스 논리를 작성하는 데 집중해야 합니다.  
  
 에 대 한 자세한 내용은 `LINQDataSource`를 참조 하세요 [LinqDataSource 웹 서버 컨트롤 개요](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))합니다.  
  
## <a name="see-also"></a>참고자료

- [LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
