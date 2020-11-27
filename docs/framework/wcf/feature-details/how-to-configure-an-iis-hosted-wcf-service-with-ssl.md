---
title: '방법: SSL을 사용하여 IIS에서 호스팅되는 WCF 서비스 구성'
description: Iis에 등록 된 인증서가 필요한 HTTP 전송 보안을 사용 하도록 IIS에서 호스팅되는 WCF 서비스를 설정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 960005761d3bed917142141976e9f9094094b34c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257654"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="cb059-103">방법: SSL을 사용하여 IIS에서 호스팅되는 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="cb059-103">How to: Configure an IIS-hosted WCF service with SSL</span></span>

<span data-ttu-id="cb059-104">이 항목에서는 HTTP 전송 보안을 사용하도록 IIS에서 호스트되는 WCF 서비스를 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-104">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="cb059-105">HTTP 전송 보안에는 IIS에 등록할 SSL 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-105">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="cb059-106">SSL 인증서가 없는 경우에는 IIS를 사용하여 테스트 인증서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-106">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="cb059-107">그런 다음 SSL 바인딩을 웹 사이트에 추가하고 웹 사이트의 인증 속성을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-107">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="cb059-108">마지막으로, HTTPS를 사용하도록 WCF 서비스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-108">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="cb059-109">자체 서명된 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="cb059-109">Creating a Self-Signed Certificate</span></span>  
  
1. <span data-ttu-id="cb059-110">인터넷 정보 서비스 관리자(inetmgr.exe)를 열고 왼쪽 트리 뷰에서 컴퓨터 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-110">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="cb059-111">화면 오른쪽에서 서버 인증서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-111">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="cb059-112">![IIS Manager 홈 화면](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="cb059-112">![IIS Manager Home Screen](media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2. <span data-ttu-id="cb059-113">서버 인증서 창에서 **Self-Signed 인증서 만들기** ...를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-113">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="cb059-114">링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-114">Link.</span></span>  
  
     <span data-ttu-id="cb059-115">![IIS를 사용 하 여 자체&#45;서명 된 인증서 만들기](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="cb059-115">![Creating a self&#45;signed certificate with IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3. <span data-ttu-id="cb059-116">자체 서명 된 인증서의 이름을 입력 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-116">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="cb059-117">![자체&#45;서명 된 인증서 만들기 대화 상자](media/mg-mycert.jpg "mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="cb059-117">![Create Self&#45;Signed Certificate Dialog](media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="cb059-118">이제 새로 만든 자체 서명 된 인증서 정보가 **서버 인증서** 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-118">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="cb059-119">![서버 인증서 창](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="cb059-119">![Server Certificate Window](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="cb059-120">생성된 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-120">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="cb059-121">SSL 바인딩 추가</span><span class="sxs-lookup"><span data-stu-id="cb059-121">Add SSL Binding</span></span>  
  
1. <span data-ttu-id="cb059-122">인터넷 정보 서비스 관리자에서 **사이트** 폴더를 확장 한 다음 화면 왼쪽의 트리 뷰에서 **기본 웹 사이트** 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-122">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2. <span data-ttu-id="cb059-123">**바인딩** ...을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-123">Click the **Bindings….**</span></span> <span data-ttu-id="cb059-124">창 오른쪽 위에 있는 **동작** 섹션의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-124">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="cb059-125">![SSL 바인딩 추가](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="cb059-125">![Adding an SSL binding](media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3. <span data-ttu-id="cb059-126">사이트 바인딩 창에서 **추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-126">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="cb059-127">![사이트 바인딩 대화 상자](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="cb059-127">![Site Bindings Dialog](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4. <span data-ttu-id="cb059-128">**사이트 바인딩 추가** 대화 상자에서 유형에 대해 https를 선택 하 고 방금 만든 자체 서명 된 인증서의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-128">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="cb059-129">![사이트 바인딩 예제](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="cb059-129">![Site binding example](media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="cb059-130">SSL용 가상 디렉터리 구성</span><span class="sxs-lookup"><span data-stu-id="cb059-130">Configure Virtual Directory for SSL</span></span>  
  
1. <span data-ttu-id="cb059-131">인터넷 정보 서비스 관리자에서 WCF 보안 서비스를 포함하는 가상 디렉터리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-131">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2. <span data-ttu-id="cb059-132">창의 가운데 창에서 IIS 섹션의 **SSL 설정** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-132">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="cb059-133">![가상 디렉터리에 대한 SSL 설정](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="cb059-133">![SSL Settings for virtual directory](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3. <span data-ttu-id="cb059-134">SSL 설정 창에서 **Ssl 필요** 확인란을 선택 하 고 화면 오른쪽의 **작업** 섹션에서 **적용** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-134">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="cb059-135">![가상 디렉터리 SSL 설정](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="cb059-135">![Virtual directory SSL settings](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="cb059-136">HTTP 전송 보안을 위한 WCF 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="cb059-136">Configure WCF Service for HTTP Transport Security</span></span>  
  
1. <span data-ttu-id="cb059-137">WCF 서비스의 web.config에서 다음 XML에 표시된 것처럼 전송 보안을 사용하도록 HTTP 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-137">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2. <span data-ttu-id="cb059-138">다음 XML에 표시된 것처럼 서비스 및 서비스 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-138">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="cb059-139">예제</span><span class="sxs-lookup"><span data-stu-id="cb059-139">Example</span></span>  

 <span data-ttu-id="cb059-140">다음은 HTTP 전송 보안을 사용하는 WCF 서비스에 대한 web.config 파일의 전체 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="cb059-140">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb059-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb059-141">See also</span></span>

- [<span data-ttu-id="cb059-142">인터넷 정보 서비스에서의 호스팅</span><span class="sxs-lookup"><span data-stu-id="cb059-142">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="cb059-143">인터넷 정보 서비스 호스팅 지침</span><span class="sxs-lookup"><span data-stu-id="cb059-143">Internet Information Service Hosting Instructions</span></span>](../samples/internet-information-service-hosting-instructions.md)
- [<span data-ttu-id="cb059-144">인터넷 정보 서비스 호스팅을 위한 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="cb059-144">Internet Information Services Hosting Best Practices</span></span>](internet-information-services-hosting-best-practices.md)
- [<span data-ttu-id="cb059-145">인라인 코드를 사용한 IIS 호스팅</span><span class="sxs-lookup"><span data-stu-id="cb059-145">IIS Hosting Using Inline Code</span></span>](../samples/iis-hosting-using-inline-code.md)
