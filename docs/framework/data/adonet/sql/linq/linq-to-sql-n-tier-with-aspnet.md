---
title: ASP.NET을 사용하는 LINQ to SQL N 계층
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 1af7f0d78f16e25c1ae7bf563c6abfb3b77f6183
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559228"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>ASP.NET을 사용하는 LINQ to SQL N 계층
을 사용 하는 ASP.NET 응용 프로그램에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Web.UI.WebControls.LinqDataSource> 웹 서버 컨트롤을 사용 합니다. 컨트롤은에 대해 쿼리 하는 데 필요한 대부분의 논리를 처리 하 고, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 데이터를 브라우저에 전달 하 고, 검색 한 다음, 데이터베이스를 업데이트 하는에 전송 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> . 컨트롤을 태그에 구성하기만 하면 컨트롤이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 과 브라우저 사이의 모든 데이터 전송을 처리합니다. 컨트롤은 프레젠테이션 계층과의 상호 작용을 처리 하 고 데이터 계층과의 통신을 처리 하기 때문에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ASP.NET 다계층 응용 프로그램의 주요 초점은 사용자 지정 비즈니스 논리를 작성 하는 것입니다.  
  
 에 대 한 자세한 내용은 `LINQDataSource` [LinqDataSource 웹 서버 컨트롤 개요](/previous-versions/aspnet/bb547113(v=vs.100))를 참조 하세요.  
  
## <a name="see-also"></a>참조

- [LINQ to SQL를 사용 하는 N 계층 및 원격 응용 프로그램](n-tier-and-remote-applications-with-linq-to-sql.md)
