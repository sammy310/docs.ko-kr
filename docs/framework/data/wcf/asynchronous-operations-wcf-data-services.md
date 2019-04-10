---
title: 비동기 작업(WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: ef41b458a3f5b977eaaff523413c1a8d3b1982a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126644"
---
# <a name="asynchronous-operations-wcf-data-services"></a>비동기 작업(WCF Data Services)
웹 응용 프로그램의 경우 내부 네트워크 내에서 실행되는 응용 프로그램보다 클라이언트와 서버 간에 보다 긴 대기 시간을 허용해야 합니다. 응용 프로그램의 성능과 사용자 환경을 최적화하려면 웹을 통해 <xref:System.Data.Services.Client.DataServiceContext> 서버에 액세스할 때 <xref:System.Data.Services.Client.DataServiceQuery%601> 및 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클래스의 비동기 메서드를 사용하는 것이 좋습니다.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 서버가 HTTP 요청을 비동기적으로 처리하지만 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리의 일부 메서드는 동기적이며 실행을 계속하기 전에 전체 요청-응답 교환이 완료될 때까지 기다립니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리의 비동기 메서드는 이 교환이 완료될 때까지 기다리지 않으며 그 동안에 응용 프로그램에서 사용자 인터페이스의 응답을 유지할 수 있도록 합니다.  
  
 메서드 쌍을 사용 하 여 비동기 작업을 수행할 수 있습니다는 <xref:System.Data.Services.Client.DataServiceContext> 하 고 <xref:System.Data.Services.Client.DataServiceQuery%601> 로 시작 하는 클래스 *시작* 및 *끝* 각각. 합니다 *시작* 메서드는 작업이 완료 될 때 서비스에서 호출 하는 대리자를 등록 합니다. 합니다 *최종* 완료 된 작업의 콜백을 처리 하도록 등록 된 대리자에서 메서드를 호출 해야 합니다. 호출 하는 경우는 *끝* 비동기 작업을 완료 하는 방법에서 동일 해야 <xref:System.Data.Services.Client.DataServiceQuery%601> 또는 <xref:System.Data.Services.Client.DataServiceContext> 작업을 시작 하는 데는 인스턴스. 각 *시작할* 메서드를 `state` 콜백에 상태 개체를 전달할 수 있는 매개 변수입니다. 이 상태 개체에서 검색 되는 <xref:System.IAsyncResult> 콜백을 사용 하 여 제공 되 고 해당 호출 하는 데 사용 됩니다 *끝* 비동기 작업을 완료 하는 방법입니다. 예를 들어, <xref:System.Data.Services.Client.DataServiceQuery%601> 인스턴스의 `state` 메서드를 호출할 때 이 인스턴스를 <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> 매개 변수로 제공하면 동일한 <xref:System.Data.Services.Client.DataServiceQuery%601> 인스턴스가 <xref:System.IAsyncResult>에 의해 반환됩니다. 이 <xref:System.Data.Services.Client.DataServiceQuery%601> 인스턴스는 <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> 메서드를 호출하여 쿼리 작업을 완료하는 데 사용됩니다. 자세한 내용은 [방법: 비동기 데이터 서비스 쿼리 실행](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md)합니다.  
  
> [!NOTE]
>  Silverlight용 .NET Framework에서 제공되는 클라이언트 라이브러리는 비동기 작업만 지원합니다. 자세한 내용은 [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)합니다.  
  
 .NET Framework 클라이언트 라이브러리는 다음 비동기 작업을 지원합니다.  
  
|작업|메서드|  
|---------------|-------------|  
|<xref:System.Data.Services.Client.DataServiceQuery%601> 실행|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|<xref:System.Data.Services.Client.DataServiceContext>에서 쿼리 실행|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|<xref:System.Data.Services.Client.DataServiceContext>에서 일괄 처리 쿼리 실행|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|<xref:System.Data.Services.Client.DataServiceContext>에 관련 엔터티 로드|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|개체에 변경 내용을 저장 하는 <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>비동기 작업에 대한 스레딩 고려 사항  
 다중 스레드 응용 프로그램에서 비동기 작업의 콜백으로 등록 된 대리자가 호출 되지 않습니다 반드시는 호출 하는 데 사용 된 동일한 스레드에서 합니다 *시작* 메서드를 하면 초기 요청이 만들어집니다. 특정 스레드에서 콜백을 호출 해야 합니다는 응용 프로그램에서 명시적으로 마샬링해야 실행 합니다 *최종* 원하는 스레드에 응답을 처리 하는 메서드. 예를 들어, WPF(Windows Presentation Foundation) 기반 응용 프로그램과 Silverlight 기반 응용 프로그램에서는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 개체의 <xref:System.Windows.Threading.Dispatcher> 메서드를 사용하여 응답을 UI 스레드로 다시 마샬링해야 합니다. 자세한 내용은 [데이터 서비스 (WCF Data Services/Silverlight) 쿼리](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95))합니다.  
  
## <a name="see-also"></a>참고자료

- [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
