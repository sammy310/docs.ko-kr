---
title: '방법: WebRequest 클래스를 사용하여 데이터 요청'
ms.date: 03/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
ms.openlocfilehash: e670a2a503ce704eff847e9e0b3ee340ab52fe62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048161"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="4abfb-102">방법: WebRequest 클래스를 사용하여 데이터 요청</span><span class="sxs-lookup"><span data-stu-id="4abfb-102">How to: Request data by using the WebRequest class</span></span>

<span data-ttu-id="4abfb-103">다음 프로시저에서는 서버에서 웹 페이지 또는 파일과 같은 리소스를 요청하는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-103">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="4abfb-104">리소스는 URI로 식별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-104">The resource must be identified by a URI.</span></span>

## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="4abfb-105">호스트 서버의 데이터를 요청하려면</span><span class="sxs-lookup"><span data-stu-id="4abfb-105">To request data from a host server</span></span>

1. <span data-ttu-id="4abfb-106">리소스 URI를 통해 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>를 호출하여 <xref:System.Net.WebRequest> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="4abfb-107">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4abfb-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("https://docs.microsoft.com");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("https://docs.microsoft.com")
    ```

    > [!NOTE]
    > <span data-ttu-id="4abfb-108">.NET Framework에서는 *http:* , *https:* , *ftp:* 및 *file:* 로 시작하는 URI에 대해 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스에서 파생된 프로토콜 지정 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="4abfb-109">그러나 프로토콜 지정 속성을 설정하거나 읽어야 하는 경우 <xref:System.Net.WebRequest> 또는 <xref:System.Net.WebResponse> 개체를 프로토콜 특정 개체 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="4abfb-110">자세한 내용은 [플러그형 프로토콜 프로그래밍](programming-pluggable-protocols.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4abfb-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="4abfb-111">`WebRequest` 개체에서 필요한 속성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="4abfb-112">예를 들어 인증을 사용하도록 설정하려면 <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> 속성을 <xref:System.Net.NetworkCredential> 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="4abfb-113"><xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>를 호출하여 요청을 서버에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-113">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4abfb-114">이 메서드는 서버 응답을 포함하는 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-114">This method returns an object containing the server's response.</span></span> <span data-ttu-id="4abfb-115">반환된 <xref:System.Net.WebResponse> 개체의 형식은 요청 URI 구성표에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-115">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="4abfb-116">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4abfb-116">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

4. <span data-ttu-id="4abfb-117">`WebResponse` 개체의 속성에 액세스하거나 프로토콜 지정 인스턴스로 캐스팅하여 프로토콜 지정 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-117">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="4abfb-118">예를 들어 <xref:System.Net.HttpWebResponse>의 HTTP 지정 속성에 액세스하려면 `WebResponse` 개체를 `HttpWebResponse` 참조로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-118">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="4abfb-119">다음 코드 예제에서는 응답과 함께 전송된 HTTP 지정 <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> 속성을 표시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-119">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)
    ```

5. <span data-ttu-id="4abfb-120">서버에서 전송된 응답 데이터를 포함하는 스트림을 가져오려면 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-120">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4abfb-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4abfb-121">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

6. <span data-ttu-id="4abfb-122">응답 개체에서 데이터를 읽은 후에 <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> 메서드를 사용하여 해당 개체를 닫거나 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 메서드를 사용하여 응답 스트림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-122">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4abfb-123">응답 개체나 스트림을 닫지 않으면 애플리케이션이 서버 연결을 모두 사용하여 추가 요청을 처리하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-123">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="4abfb-124">`WebResponse.Close` 메서드가 응답을 닫으면 `Stream.Close`를 호출하기 때문에 모든 응답 및 스트림 개체에서 `Close`를 호출할 필요가 없지만 유해하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-124">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="4abfb-125">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4abfb-125">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="4abfb-126">예제</span><span class="sxs-lookup"><span data-stu-id="4abfb-126">Example</span></span>

<span data-ttu-id="4abfb-127">다음 코드 예제에서는 웹 서버에 데이터를 만들고 응답에서 데이터를 읽는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4abfb-127">The following code example shows how to create a request to a web server and read the data in its response:</span></span>

[!code-csharp[RequestDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/RequestDataUsingWebRequest/cs/WebRequestGetExample.cs)]
[!code-vb[RequestDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/RequestDataUsingWebRequest/vb/WebRequestGetExample.vb)]

## <a name="see-also"></a><span data-ttu-id="4abfb-128">참조</span><span class="sxs-lookup"><span data-stu-id="4abfb-128">See also</span></span>

- [<span data-ttu-id="4abfb-129">인터넷 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="4abfb-129">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="4abfb-130">네트워크에서 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="4abfb-130">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="4abfb-131">프록시를 통해 인터넷에 액세스</span><span class="sxs-lookup"><span data-stu-id="4abfb-131">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="4abfb-132">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="4abfb-132">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="4abfb-133">방법: WebRequest 클래스를 사용하여 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="4abfb-133">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
