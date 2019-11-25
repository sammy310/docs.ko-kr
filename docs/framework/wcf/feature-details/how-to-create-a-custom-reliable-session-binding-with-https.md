---
title: '방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 26466a97ae44e6852c189d0b72bdba1b93d86141
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141728"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a><span data-ttu-id="c099b-102">방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="c099b-102">How to: Create a Custom Reliable Session Binding with HTTPS</span></span>

<span data-ttu-id="c099b-103">이 항목에서는 신뢰할 수 있는 세션에 SSL(Secure Sockets Layer) 전송 보안을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-103">This topic demonstrates the use of Secure Sockets Layer (SSL) transport security with reliable sessions.</span></span> <span data-ttu-id="c099b-104">HTTPS를 통해 신뢰할 수 있는 세션을 사용하려면 신뢰할 수 있는 세션 및 HTTPS 전송을 사용하는 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-104">To use a reliable session over HTTPS, you must create a custom binding that uses a reliable session and the HTTPS transport.</span></span> <span data-ttu-id="c099b-105">코드를 사용 하 여 명령적으로 또는 구성 파일에서 선언적으로 신뢰할 수 있는 세션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-105">You enable the reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="c099b-106">이 절차에서는 클라이언트 및 서비스 구성 파일을 사용 하 여 신뢰할 수 있는 세션과 [ **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) 요소를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-106">This procedure uses the client and service configuration files to enable the reliable session and the [**\<httpsTransport>**](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) element.</span></span>

<span data-ttu-id="c099b-107">이 절차의 핵심 부분은 **\<끝점 >** 구성 요소에 `reliableSessionOverHttps`이라는 사용자 지정 바인딩 구성을 참조 하는 `bindingConfiguration` 특성이 포함 되어 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-107">The key part of this procedure is that the **\<endpoint>** configuration element contain a `bindingConfiguration` attribute that references a custom binding configuration named `reliableSessionOverHttps`.</span></span> <span data-ttu-id="c099b-108">[ **\<binding >** ](../../configure-apps/file-schema/wcf/bindings.md) 구성 요소는 **\<reliableSession >** 및 **\<httpsTransport >** 요소를 포함 하 여 신뢰할 수 있는 세션 및 HTTPS 전송을 사용 하도록 지정 하기 위해이 이름을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-108">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element references this name to specify that a reliable session and the HTTPS transport are used by including **\<reliableSession>** and **\<httpsTransport>** elements.</span></span>

<span data-ttu-id="c099b-109">이 예제의 소스 복사에 대해서는 HTTPS를 [통한 사용자 지정 바인딩 신뢰할 수 있는 세션](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c099b-109">For the source copy of this example, see [Custom Binding Reliable Session over HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).</span></span>

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="c099b-110">HTTPS를 사용 하 여 신뢰할 수 있는 세션을 사용 하도록 서비스를 CustomBinding으로 구성</span><span class="sxs-lookup"><span data-stu-id="c099b-110">Configure the service with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="c099b-111">서비스 유형에 대한 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. <span data-ttu-id="c099b-112">서비스 클래스에 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="c099b-113">주소 또는 바인딩 정보는 서비스 구현 내에 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="c099b-114">구성 파일에서 주소 또는 바인딩 정보를 검색 하는 코드를 작성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. <span data-ttu-id="c099b-115">신뢰할 수 있는 세션 및 HTTPS 전송을 사용 하는 `reliableSessionOverHttps` 이라는 사용자 지정 바인딩을 사용 하 여 `CalculatorService`에 대 한 끝점을 구성 *하는 web.config 파일을* 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` with a custom binding named `reliableSessionOverHttps` that uses a reliable session and the HTTPS transport.</span></span>

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. <span data-ttu-id="c099b-116">줄이 포함 된 *서비스 .svc* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-116">Create a *Service.svc* file that contains the line:</span></span>

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. <span data-ttu-id="c099b-117">인터넷 정보 서비스 (IIS) 가상 디렉터리에 *서비스 .svc* 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a><span data-ttu-id="c099b-118">HTTPS로 신뢰할 수 있는 세션을 사용 하도록 CustomBinding을 사용 하 여 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="c099b-118">Configure the client with a CustomBinding to use a reliable session with HTTPS</span></span>

1. <span data-ttu-id="c099b-119">명령줄에서 [ServiceModel Metadata 유틸리티 도구 (*svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 서비스 메타 데이터에서 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="c099b-120">생성 된 클라이언트에는 클라이언트 구현에서 충족 해야 하는 서비스 계약을 정의 하는 `ICalculator` 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-120">The client that's generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. <span data-ttu-id="c099b-121">또한 생성된 클라이언트 애플리케이션에는 `ClientCalculator`의 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="c099b-122">주소 및 바인딩 정보는 서비스 구현 내에 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-122">Note that the address and binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="c099b-123">구성 파일에서 주소 및 바인딩 정보를 검색 하는 코드를 작성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-123">You aren't required to write code to retrieve the address and binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. <span data-ttu-id="c099b-124">HTTPS 전송 및 신뢰할 수 있는 세션을 사용 하도록 `reliableSessionOverHttps` 이라는 사용자 지정 바인딩을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-124">Configure a custom binding named `reliableSessionOverHttps` to use the HTTPS transport and reliable sessions.</span></span>

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. <span data-ttu-id="c099b-125">애플리케이션에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-125">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. <span data-ttu-id="c099b-126">클라이언트를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c099b-126">Compile and run the client.</span></span>  

## <a name="net-framework-security"></a><span data-ttu-id="c099b-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="c099b-127">.NET Framework security</span></span>

<span data-ttu-id="c099b-128">이 샘플에 사용 된 인증서는 Makecert.exe를 사용 하 여 만든 테스트 인증서 이므로 브라우저에서 `https://localhost/servicemodelsamples/service.svc`와 같은 HTTPS 주소에 액세스 하려고 하면 보안 경고가 나타납니다 *.*</span><span class="sxs-lookup"><span data-stu-id="c099b-128">Because the certificate used in this sample is a test certificate created with *Makecert.exe*, a security alert appears when you try to access an HTTPS address, such as `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="c099b-129">참조</span><span class="sxs-lookup"><span data-stu-id="c099b-129">See also</span></span>

- [<span data-ttu-id="c099b-130">신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="c099b-130">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
