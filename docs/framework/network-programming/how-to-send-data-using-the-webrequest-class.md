---
title: '방법: WebRequest 클래스를 사용하여 데이터 보내기'
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 591a1129625a4ff08c9aa37ce651bbc0320ff25d
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634273"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a><span data-ttu-id="a39dd-102">방법: WebRequest 클래스를 사용하여 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="a39dd-102">How to: Send data by using the WebRequest class</span></span>
<span data-ttu-id="a39dd-103">다음 프로시저에서는 서버에 데이터를 보내는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-103">The following procedure describes the steps to send data to a server.</span></span> <span data-ttu-id="a39dd-104">이 프로시저는 일반적으로 웹 페이지에 데이터를 게시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-104">This procedure is commonly used to post data to a Web page.</span></span> 
  
## <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="a39dd-105">호스트에 데이터를 보내려면</span><span class="sxs-lookup"><span data-stu-id="a39dd-105">To send data to a host server</span></span>  
  
1.  <span data-ttu-id="a39dd-106">스크립트 또는 ASP.NET 페이지와 같이 데이터를 허용하는 리소스의 URI에서 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>을 호출하여 <xref:System.Net.WebRequest> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource, such as a script or ASP.NET page, that accepts data.</span></span> <span data-ttu-id="a39dd-107">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-107">For example:</span></span> 
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="a39dd-108">.NET Framework에서는 *http:*, *https:*, *ftp:* 및 *file:* 로 시작하는 URI에 대해 <xref:System.Net.WebRequest> 및 <xref:System.Net.WebResponse> 클래스에서 파생된 프로토콜 지정 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>
    <span data-ttu-id="a39dd-109">그러나 프로토콜 지정 속성을 설정하거나 읽어야 하는 경우 <xref:System.Net.WebRequest> 또는 <xref:System.Net.WebResponse> 개체를 프로토콜 특정 개체 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="a39dd-110">자세한 내용은 [플러그형 프로토콜 프로그래밍](programming-pluggable-protocols.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a39dd-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span> 
  
2.  <span data-ttu-id="a39dd-111">`WebRequest` 개체에서 필요한 속성 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="a39dd-112">예를 들어 인증을 사용하도록 설정하려면 <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> 속성을 <xref:System.Net.NetworkCredential> 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
3.  <span data-ttu-id="a39dd-113">요청을 통해 데이터를 보내도록 허용하는 프로토콜 메서드를 지정합니다(예: HTTP `POST` 메서드).</span><span class="sxs-lookup"><span data-stu-id="a39dd-113">Specify a protocol method that permits data to be sent with a request, such as the HTTP `POST` method:</span></span>  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  <span data-ttu-id="a39dd-114"><xref:System.Web.HttpRequest.ContentLength> 속성을 요청에 포함된 바이트 수로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-114">Set the <xref:System.Web.HttpRequest.ContentLength> property to the number of bytes you're including with your request.</span></span> <span data-ttu-id="a39dd-115">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-115">For example:</span></span> 
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  <span data-ttu-id="a39dd-116"><xref:System.Web.HttpRequest.ContentType> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-116">Set the <xref:System.Web.HttpRequest.ContentType> property to an appropriate value.</span></span> <span data-ttu-id="a39dd-117">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-117">For example:</span></span>
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  <span data-ttu-id="a39dd-118"><xref:System.Net.WebRequest.GetRequestStream%2A> 메서드를 호출하여 요청 데이터를 포함하는 스트림을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-118">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span> <span data-ttu-id="a39dd-119">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-119">For example:</span></span>
  
    ```csharp  
    Stream dataStream = request.GetRequestStream();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream()  
    ```  
  
7.  <span data-ttu-id="a39dd-120">`GetRequestStream` 메서드에서 반환된 <xref:System.IO.Stream> 개체에 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-120">Write the data to the <xref:System.IO.Stream> object returned by the `GetRequestStream` method.</span></span> <span data-ttu-id="a39dd-121">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-121">For example:</span></span>
  
    ```csharp  
    dataStream.Write(byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write(byteArray, 0, byteArray.Length)  
    ```  
  
8.  <span data-ttu-id="a39dd-122"><xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 메서드를 호출하여 요청 스트림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-122">Close the request stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a39dd-123">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-123">For example:</span></span>
  
    ```csharp  
    dataStream.Close();  
    ```  
  
    ```vb  
    dataStream.Close()  
    ```  
  
9. <span data-ttu-id="a39dd-124"><xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>를 호출하여 요청을 서버에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-124">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a39dd-125">이 메서드는 서버 응답을 포함하는 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-125">This method returns an object containing the server's response.</span></span> <span data-ttu-id="a39dd-126">반환된 `WebResponse` 개체의 형식은 요청 URI 구성표에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-126">The returned `WebResponse` object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="a39dd-127">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-127">For example:</span></span>
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
10. <span data-ttu-id="a39dd-128">`WebResponse` 개체의 속성에 액세스하거나 프로토콜 지정 인스턴스로 캐스팅하여 프로토콜 지정 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-128">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span> 

    <span data-ttu-id="a39dd-129">예를 들어 <xref:System.Net.HttpWebResponse>의 HTTP 지정 속성에 액세스하려면 `WebResponse` 개체를 <xref:System.Net.HttpWebResponse> 참조로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an <xref:System.Net.HttpWebResponse> reference.</span></span> <span data-ttu-id="a39dd-130">다음 코드 예제에서는 응답과 함께 전송된 HTTP 지정 <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> 속성을 표시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-130">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>
  
    ```csharp  
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);    
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. <span data-ttu-id="a39dd-131">서버에서 전송된 응답 데이터를 포함하는 스트림을 가져오려면 `WebResponse` 개체의 <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-131">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method of your `WebResponse` object.</span></span> <span data-ttu-id="a39dd-132">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-132">For example:</span></span>
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
12. <span data-ttu-id="a39dd-133">응답 개체에서 데이터를 읽은 후에 <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> 메서드를 사용하여 해당 개체를 닫거나 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 메서드를 사용하여 응답 스트림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-133">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a39dd-134">응답이나 스트림을 닫지 않으면 애플리케이션이 서버 연결을 모두 사용하여 추가 요청을 처리하지 못하게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-134">If you don't close either the response or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="a39dd-135">`WebResponse.Close` 메서드가 응답을 닫으면 `Stream.Close`를 호출하기 때문에 모든 응답 및 스트림 개체에서 `Close`를 호출할 필요가 없지만 유해하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-135">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="a39dd-136">예:</span><span class="sxs-lookup"><span data-stu-id="a39dd-136">For example:</span></span>
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="a39dd-137">예제</span><span class="sxs-lookup"><span data-stu-id="a39dd-137">Example</span></span>  
  
<span data-ttu-id="a39dd-138">다음 코드 예제에서는 웹 서버에 데이터를 보내고 응답에서 데이터를 읽는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a39dd-138">The following code example shows how to send data to a web server and read the data in its response:</span></span>  

```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main()  
        {  
            // Create a request by using a URL that can receive a post.   
            WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  

            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes(postData);  

            // Set the ContentType property of the request.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the request.  
            request.ContentLength = byteArray.Length;  

            // Get the request stream.  
            Stream dataStream = request.GetRequestStream();  
            // Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length);  
            // Close the stream.  
            dataStream.Close();  

            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine(((HttpWebResponse)response).StatusDescription);  

            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream();  
            // Open the stream by using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  

            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  

            // Clean up the response.  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  

Namespace Examples.System.Net  

    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  

            ' Create a request by using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  

            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  

            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  

            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the stream.  
            dataStream.Close()  

            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  

            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream by using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  

            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  

            ' Clean up the response.  
            reader.Close()  
            response.Close()  

        End Sub  

    End Class  

End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="a39dd-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a39dd-139">See also</span></span>
- [<span data-ttu-id="a39dd-140">인터넷 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="a39dd-140">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="a39dd-141">네트워크에서 스트림 사용</span><span class="sxs-lookup"><span data-stu-id="a39dd-141">Using streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="a39dd-142">프록시를 통해 인터넷에 액세스</span><span class="sxs-lookup"><span data-stu-id="a39dd-142">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="a39dd-143">데이터 요청</span><span class="sxs-lookup"><span data-stu-id="a39dd-143">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="a39dd-144">방법: WebRequest 클래스를 사용하여 데이터 요청</span><span class="sxs-lookup"><span data-stu-id="a39dd-144">How to: Request data by using the WebRequest class</span></span>](how-to-request-data-using-the-webrequest-class.md)
