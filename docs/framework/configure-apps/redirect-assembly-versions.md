---
title: 어셈블리 버전 리디렉션
description: 컴파일 시간 바인딩 참조를 다른 버전의 .NET 어셈블리, 타사 어셈블리 또는 고유의 앱 어셈블리로 리디렉션합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- assembly binding, redirection
- redirecting assembly binding to earlier version
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], binding redirection
ms.assetid: 88fb1a17-6ac9-4b57-8028-193aec1f727c
ms.openlocfilehash: 4cfd4336fb9999c996bea28eb86f1143932d4c51
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141736"
---
# <a name="redirecting-assembly-versions"></a><span data-ttu-id="bba74-103">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="bba74-103">Redirecting Assembly Versions</span></span>

<span data-ttu-id="bba74-104">.NET Framework 어셈블리, 타사 어셈블리 또는 고유의 앱 어셈블리로 컴파일 타임 바인딩 참조를 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-104">You can redirect compile-time binding references to .NET Framework assemblies, third-party assemblies, or your own app's assemblies.</span></span> <span data-ttu-id="bba74-105">게시자 정책, 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일 등을 통한 다양한 방법으로 여러 버전의 어셈블리를 사용하도록 응용 프로그램을 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-105">You can redirect your app to use a different version of an assembly in a number of ways: through publisher policy, through an app configuration file; or through the machine configuration file.</span></span> <span data-ttu-id="bba74-106">이 문서에서는 .NET Framework에서 어셈블리 바인딩의 작동 방식과 구성 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-106">This article discusses how assembly binding works in the .NET Framework and how it can be configured.</span></span>

<a name="BKMK_Assemblyunificationanddefaultbinding"></a>
## <a name="assembly-unification-and-default-binding"></a><span data-ttu-id="bba74-107">어셈블리 통합 및 기본 바인딩</span><span class="sxs-lookup"><span data-stu-id="bba74-107">Assembly unification and default binding</span></span>
 <span data-ttu-id="bba74-108">.NET Framework 어셈블리에 대한 바인딩은 *어셈블리 통합*이라고 하는 프로세스를 통해 리디렉션되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-108">Bindings to .NET Framework assemblies are sometimes redirected through a process called *assembly unification*.</span></span> <span data-ttu-id="bba74-109">.NET Framework는 공용 언어 런타임 버전과 형식 라이브러리를 구성하는 약 24개의 .NET Framework 어셈블리로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-109">The .NET Framework consists of a version of the common language runtime and about two dozen .NET Framework assemblies that make up the type library.</span></span> <span data-ttu-id="bba74-110">이러한 .NET Framework 어셈블리는 런타임에서 하나의 단위로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-110">These .NET Framework assemblies are treated by the runtime as a single unit.</span></span> <span data-ttu-id="bba74-111">기본적으로, 응용 프로그램이 시작되면 런타임으로 실행되는 코드의 형식에 대한 모든 참조는 프로세스에서 로드되는 런타임과 버전 번호가 같은 .NET Framework 어셈블리로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-111">By default, when an app is launched, all references to types in code run by the runtime are directed to .NET Framework assemblies that have the same version number as the runtime that is loaded in a process.</span></span> <span data-ttu-id="bba74-112">이 모델에서 발생하는 리디렉션은 런타임에 대한 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-112">The redirections that occur with this model are the default behavior for the runtime.</span></span>

 <span data-ttu-id="bba74-113">예를 들어 앱이 System.XML 네임 스페이스의 형식을 참조 하 고 .NET Framework 4.5를 사용 하 여 빌드된 경우, 런타임 버전 4.5과 함께 제공 되는 System.XML 어셈블리에 대 한 정적 참조를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-113">For example, if your app references types in the System.XML namespace and was built by using the .NET Framework 4.5, it contains static references to the System.XML assembly that ships with runtime version 4.5.</span></span> <span data-ttu-id="bba74-114">.NET Framework 4와 함께 제공되는 System.XML 어셈블리를 가리키도록 바인딩 참조를 리디렉션하려는 경우에는 응용 프로그램 구성 파일에 리디렉션 정보를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-114">If you want to redirect the binding reference to point to the System.XML assembly that ship with the .NET Framework 4, you can put redirect information in the app configuration file.</span></span> <span data-ttu-id="bba74-115">통합된 .NET Framework 어셈블리에 대한 구성 파일에서 바인딩 리디렉션은 해당 어셈블리에 대한 통합을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-115">A binding redirection in a configuration file for a unified .NET Framework assembly cancels the unification for that assembly.</span></span>

 <span data-ttu-id="bba74-116">또한 여러 버전을 사용할 수 있는 경우 타사 어셈블리에 대해 어셈블리 바인딩을 수동으로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-116">In addition, you may want to manually redirect assembly binding for third-party assemblies if there are multiple versions available.</span></span>

<a name="BKMK_Redirectingassemblyversionsbyusingpublisherpolicy"></a>
## <a name="redirecting-assembly-versions-by-using-publisher-policy"></a><span data-ttu-id="bba74-117">게시자 정책을 사용하여 어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="bba74-117">Redirecting assembly versions by using publisher policy</span></span>
 <span data-ttu-id="bba74-118">어셈블리 공급업체는 새 어셈블리와 함께 게시자 정책 파일을 포함하여 최신 버전의 어셈블리로 응용 프로그램을 유도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-118">Vendors of assemblies can direct apps to a newer version of an assembly by including a publisher policy file with the new assembly.</span></span> <span data-ttu-id="bba74-119">전역 어셈블리 캐시에 있는 게시자 정책 파일에는 어셈블리 리디렉션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-119">The publisher policy file, which is located in the global assembly cache, contains assembly redirection settings.</span></span>

 <span data-ttu-id="bba74-120">각 *주*.*부* 버전의 어셈블리에는 자체 게시자 정책 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-120">Each *major*.*minor* version of an assembly has its own publisher policy file.</span></span> <span data-ttu-id="bba74-121">예를 들어 버전 2.0.2.222에서 2.0.3.000으로 리디렉션과 버전 2.0.2.321에서 2.0.3.000으로 리디렉션은 버전 2.0과 연관되기 때문에 동일한 파일로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-121">For example, redirections from version 2.0.2.222 to 2.0.3.000 and from version 2.0.2.321 to version 2.0.3.000 both go into the same file, because they are associated with version 2.0.</span></span> <span data-ttu-id="bba74-122">그러나 버전 3.0.0.999에서 4.0.0.000으로 리디렉션은 버전 3.0.999용 파일로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-122">However, a redirection from version 3.0.0.999 to version 4.0.0.000 goes into the file for version 3.0.999.</span></span> <span data-ttu-id="bba74-123">.NET Framework의 각 주 버전에는 자체 게시자 정책 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-123">Each major version of the .NET Framework has its own publisher policy file.</span></span>

 <span data-ttu-id="bba74-124">어셈블리에 대한 게시자 정책 파일이 있으면, 런타임에서 어셈블리의 매니페스트 및 응용 프로그램 구성 파일을 확인한 후 이 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-124">If a publisher policy file exists for an assembly, the runtime checks this file after checking the assembly's manifest and app configuration file.</span></span> <span data-ttu-id="bba74-125">공급업체는 새 어셈블리가 리디렉션되는 어셈블리와 역호환되는 경우에만 게시자 정책 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-125">Vendors should use publisher policy files only when the new assembly is backward compatible with the assembly being redirected.</span></span>

 <span data-ttu-id="bba74-126">[게시자 정책 무시 섹션](#bypass_PP)에 설명된 대로, 앱 구성 파일에서 설정을 지정하여 응용 프로그램의 게시자 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-126">You can bypass publisher policy for your app by specifying settings in the app configuration file, as discussed in the [Bypassing publisher policy section](#bypass_PP).</span></span>

<a name="BKMK_Redirectingassemblyversionsattheapplevel"></a>
## <a name="redirecting-assembly-versions-at-the-app-level"></a><span data-ttu-id="bba74-127">앱 수준에서 어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="bba74-127">Redirecting assembly versions at the app level</span></span>
 <span data-ttu-id="bba74-128">앱 구성 파일을 통해 앱의 바인딩 동작을 변경하는 몇 가지 방법이 있습니다. 즉, 파일을 수동으로 편집하거나, 자동 바인딩 리디렉션을 사용하거나, 게시자 정책을 무시하여 바인딩 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-128">There are a few different techniques for changing the binding behavior for your app through the app configuration file: you can manually edit the file, you can rely on automatic binding redirection, or you can specify binding behavior by bypassing publisher policy.</span></span>

### <a name="manually-editing-the-app-config-file"></a><span data-ttu-id="bba74-129">앱 프로그램 구성 파일을 수동으로 편집</span><span class="sxs-lookup"><span data-stu-id="bba74-129">Manually editing the app config file</span></span>
 <span data-ttu-id="bba74-130">앱 프로그램 구성 파일을 수동으로 편집하여 어셈블리 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-130">You can manually edit the app configuration file to resolve assembly issues.</span></span> <span data-ttu-id="bba74-131">예를 들어, 공급업체가 게시자 정책을 제공하지 않고 앱에서 사용되는 어셈블리의 최신 버전을 출시하는 경우에는 역호환성이 보장되지 않으므로 다음과 같이 앱의 구성 파일에 어셈블리 바인딩 정보를 배치하여 새 버전의 어셈블리를 사용하도록 앱을 유도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-131">For example, if a vendor might release a newer version of an assembly that your app uses without supplying a publisher policy, because they do not guarantee backward compatibility, you can direct your app to use the newer version of the assembly by putting assembly binding information in your app's configuration file as follows.</span></span>

```xml
<dependentAssembly>
  <assemblyIdentity name="someAssembly"
    publicKeyToken="32ab4ba45e0a69a1"
    culture="en-us" />
  <bindingRedirect oldVersion="7.0.0.0" newVersion="8.0.0.0" />
</dependentAssembly>
```

### <a name="relying-on-automatic-binding-redirection"></a><span data-ttu-id="bba74-132">자동 바인딩 리디렉션 사용</span><span class="sxs-lookup"><span data-stu-id="bba74-132">Relying on automatic binding redirection</span></span>

<span data-ttu-id="bba74-133">.NET Framework 4.5.1 이상 버전을 대상으로 하는 Visual Studio에서 데스크톱 앱을 만드는 경우 앱에서 자동 바인딩 리디렉션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-133">When you create a desktop app in Visual Studio that targets the .NET Framework 4.5.1 or a later version, the app uses automatic binding redirection.</span></span> <span data-ttu-id="bba74-134">즉, 두 구성 요소가 강력한 이름의 동일한 어셈블리의 다른 버전을 참조하는 경우 런타임에서 출력 앱 구성 파일(app.config)에 최신 버전의 어셈블리에 바인딩 리디렉션을 자동으로 추가한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-134">This means that if two components reference different versions of the same strong-named assembly, the runtime automatically adds a binding redirection to the newer version of the assembly in the output app configuration (app.config) file.</span></span> <span data-ttu-id="bba74-135">이 리디렉션은 그 밖에 발생할 수 있는 어셈블리 통합을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-135">This redirection overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="bba74-136">소스 app.config 파일은 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-136">The source app.config file is not modified.</span></span> <span data-ttu-id="bba74-137">예를 들어, 앱에서 대역 외 .NET Framework 구성 요소를 직접 참조하지만 동일한 구성 요소의 이전 버전을 대상으로 하는 타사 라이브러리를 사용한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-137">For example, let's say that your app directly references an out-of-band .NET Framework component but uses a third-party library that targets an older version of the same component.</span></span> <span data-ttu-id="bba74-138">앱을 컴파일하면, 최신 버전의 구성 요소에 대한 바인딩 리디렉션이 포함되도록 출력 앱 구성 파일이 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-138">When you compile the app, the output app configuration file is modified to contain a binding redirection to the newer version of the component.</span></span> <span data-ttu-id="bba74-139">웹앱을 만드는 경우, 바인딩 충돌에 대한 빌드 경고가 표시된 후에 소스 웹 구성 파일에 필요한 바인딩 리디렉션을 추가할 수 있는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-139">If you create a web app, you receive a build warning regarding the binding conflict, which in turn, gives you the option to add the necessary binding redirect to the source web configuration file.</span></span>

<span data-ttu-id="bba74-140">소스 app.config 파일에 바인딩 리디렉션을 수동으로 추가 하는 경우 (컴파일 시간에) Visual Studio에서 추가 된 바인딩 리디렉션을 기준으로 어셈블리를 통합 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-140">If you manually add binding redirects to the source app.config file, at compile time, Visual Studio tries to unify the assemblies based on the binding redirects you added.</span></span> <span data-ttu-id="bba74-141">예를 들어, 어셈블리에 대해 다음과 같은 바인딩 리디렉션을 삽입한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-141">For example, let's say you insert the following binding redirect for an assembly:</span></span>

`<bindingRedirect oldVersion="3.0.0.0" newVersion="2.0.0.0" />`

<span data-ttu-id="bba74-142">앱에 있는 다른 프로젝트가 동일한 어셈블리의 버전 1.0.0.0을 참조하는 경우, 자동 바인딩 리디렉션은 다음 항목을 출력 app.config 파일에 추가하여 이 어셈블리의 2.0.0.0 버전에 앱이 통합되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-142">If another project in your app references version 1.0.0.0 of the same assembly, automatic binding redirection adds the following entry to the output app.config file so that the app is unified on version 2.0.0.0 of this assembly:</span></span>

`<bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />`

<span data-ttu-id="bba74-143">앱이 이전 버전의 .NET Framework를 대상으로 하는 경우 자동 바인딩 리디렉션을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-143">You can enable automatic binding redirection if your app targets older versions of the .NET Framework.</span></span> <span data-ttu-id="bba74-144">모든 어셈블리에 대 한 app.config 파일에 바인딩 리디렉션 정보를 제공 하거나 바인딩 리디렉션 기능을 해제 하 여이 기본 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-144">You can override this default behavior by providing binding redirection information in the app.config file for any assembly, or by turning off the binding redirection feature.</span></span> <span data-ttu-id="bba74-145">이 기능을 설정 하거나 해제 하는 방법에 대 한 자세한 내용은 [방법: 자동 바인딩 리디렉션 사용 및 사용 안 함](how-to-enable-and-disable-automatic-binding-redirection.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bba74-145">For information about how to turn this feature on or off, see [How to: Enable and Disable Automatic Binding Redirection](how-to-enable-and-disable-automatic-binding-redirection.md).</span></span>

<a name="bypass_PP"></a>
### <a name="bypassing-publisher-policy"></a><span data-ttu-id="bba74-146">게시자 정책 무시</span><span class="sxs-lookup"><span data-stu-id="bba74-146">Bypassing publisher policy</span></span>
 <span data-ttu-id="bba74-147">필요에 따라 앱 구성 파일에서 게시자 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-147">You can override publisher policy in the app configuration file if necessary.</span></span> <span data-ttu-id="bba74-148">예를 들어, 역호환성이 있다고 하는 최신 버전의 어셈블리가 앱을 중단시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-148">For example, new versions of assemblies that claim to be backward compatible can still break an app.</span></span> <span data-ttu-id="bba74-149">게시자 정책을 무시 하려면 [\<publisherPolicy>](./file-schema/runtime/publisherpolicy-element.md) [\<dependentAssembly>](./file-schema/runtime/dependentassembly-element.md) 앱 구성 파일의 요소에 요소를 추가 하 고 **적용** 특성을 **아니요**로 설정 합니다. 그러면 모든 이전 **예** 설정이 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-149">If you want to bypass publisher policy, add a [\<publisherPolicy>](./file-schema/runtime/publisherpolicy-element.md) element to the [\<dependentAssembly>](./file-schema/runtime/dependentassembly-element.md) element in the app configuration file, and set the **apply** attribute to **no**, which overrides any previous **yes** settings.</span></span>

 `<publisherPolicy apply="no" />`

 <span data-ttu-id="bba74-150">사용자에 대해 실행 중인 앱을 유지하려면 게시자 정책을 무시할 수 있지만, 문제가 발생할 경우 어셈블리 공급업체에 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-150">Bypass publisher policy to keep your app running for your users, but make sure you report the problem to the assembly vendor.</span></span> <span data-ttu-id="bba74-151">어셈블리에 게시자 정책 파일이 있는 경우, 공급업체는 해당 어셈블리가 역호환되는지 확인하고 클라이언트에서 가능하면 최신 버전을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-151">If an assembly has a publisher policy file, the vendor should make sure that the assembly is backward compatible and that clients can use the new version as much as possible.</span></span>

<a name="BKMK_Redirectingassemblyversionsatthemachinelevel"></a>
## <a name="redirecting-assembly-versions-at-the-machine-level"></a><span data-ttu-id="bba74-152">컴퓨터 수준에서 어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="bba74-152">Redirecting assembly versions at the machine level</span></span>
 <span data-ttu-id="bba74-153">드문 경우이지만 시스템 관리자가 컴퓨터의 모든 앱에서 특정 버전의 어셈블리를 사용해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-153">There might be rare cases when a machine administrator wants all apps on a computer to use a specific version of an assembly.</span></span> <span data-ttu-id="bba74-154">예를 들어, 관리자는 모든 앱에서 보안 허점을 해결하는 특정 어셈블리 버전을 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-154">For example, the administrator might want every app to use a particular assembly version, because that version fixes a security hole.</span></span> <span data-ttu-id="bba74-155">컴퓨터의 구성 파일에서 어셈블리가 리디렉션되면, 이전 버전을 사용하는 컴퓨터의 모든 앱이 새 버전을 사용하도록 유도됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-155">If an assembly is redirected in the machine's configuration file, all apps on that machine that use the old version will be directed to use the new version.</span></span> <span data-ttu-id="bba74-156">컴퓨터 구성 파일은 앱 구성 파일 및 게시자 정책 파일을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-156">The machine configuration file overrides the app configuration file and the publisher policy file.</span></span> <span data-ttu-id="bba74-157">이 파일은 %*런타임 설치 경로*%\Config 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-157">This file is located in the %*runtime install path*%\Config directory.</span></span> <span data-ttu-id="bba74-158">일반적으로 .NET Framework는 %drive%\Windows\Microsoft.NET\Framework 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-158">Typically, the .NET Framework is installed in the %drive%\Windows\Microsoft.NET\Framework directory.</span></span>

<a name="BKMK_Specifyingassemblybindinginconfigurationfiles"></a>
## <a name="specifying-assembly-binding-in-configuration-files"></a><span data-ttu-id="bba74-159">구성 파일에 어셈블리 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="bba74-159">Specifying assembly binding in configuration files</span></span>
 <span data-ttu-id="bba74-160">동일한 XML 형식을 사용하여 앱 구성 파일, 컴퓨터 구성 파일 또는 게시자 정책 파일에 있는 바인딩 리디렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-160">You use the same XML format to specify binding redirects whether it’s in the app configuration file, the machine configuration file, or the publisher policy file.</span></span> <span data-ttu-id="bba74-161">한 어셈블리 버전을 다른 버전으로 리디렉션하려면 요소를 사용 [\<bindingRedirect>](./file-schema/runtime/bindingredirect-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-161">To redirect one assembly version to another, use the [\<bindingRedirect>](./file-schema/runtime/bindingredirect-element.md) element.</span></span> <span data-ttu-id="bba74-162">**oldVersion** 특성은 단일 어셈블리 버전 또는 다양한 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-162">The **oldVersion** attribute can specify a single assembly version or a range of versions.</span></span> <span data-ttu-id="bba74-163">`newVersion` 특성은 단일 버전을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-163">The `newVersion` attribute should specify a single version.</span></span>  <span data-ttu-id="bba74-164">예를 들어, `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` 은 런타임에서 1.1.0.0 - 1.2.0.0 버전의 어셈블리 대신 2.0.0.0 버전을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-164">For example, `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` specifies that the runtime should use version 2.0.0.0 instead of the assembly versions between 1.1.0.0 and 1.2.0.0.</span></span>

 <span data-ttu-id="bba74-165">다음 코드 예제는 다양한 바인딩 리디렉션 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-165">The following code example demonstrates a variety of binding redirect scenarios.</span></span> <span data-ttu-id="bba74-166">이 예제에서는 `myAssembly`에 대해 다양한 버전의 리디렉션을 지정하고, `mySecondAssembly`에 대해 단일 바인딩 리디렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-166">The example specifies a redirect for a range of versions for `myAssembly`, and a single binding redirect for `mySecondAssembly`.</span></span> <span data-ttu-id="bba74-167">또한 이 예제에서는 게시자 정책 파일이 `myThirdAssembly`에 대한 바인딩 리디렉션을 재정의하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-167">The example also specifies that publisher policy file will not override the binding redirects for `myThirdAssembly`.</span></span>

 <span data-ttu-id="bba74-168">어셈블리를 바인딩하려면 태그에서 xmlns 특성을 사용 하 여 문자열 "urn: 스키마-microsoft-com: **x** 1"을 지정 해야 합니다 [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) .</span><span class="sxs-lookup"><span data-stu-id="bba74-168">To bind an assembly, you must specify the string "urn:schemas-microsoft-com:asm.v1" with the **xmlns** attribute in the [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) tag.</span></span>

```xml
<configuration>
  <runtime>
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
      <dependentAssembly>
        <assemblyIdentity name="myAssembly"
          publicKeyToken="32ab4ba45e0a69a1"
          culture="en-us" />
        <!-- Assembly versions can be redirected in app,
          publisher policy, or machine configuration files. -->
        <bindingRedirect oldVersion="1.0.0.0-2.0.0.0" newVersion="3.0.0.0" />
      </dependentAssembly>
      <dependentAssembly>
        <assemblyIdentity name="mySecondAssembly"
          publicKeyToken="32ab4ba45e0a69a1"
          culture="en-us" />
             <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />
      </dependentAssembly>
      <dependentAssembly>
      <assemblyIdentity name="myThirdAssembly"
        publicKeyToken="32ab4ba45e0a69a1"
        culture="en-us" />
        <!-- Publisher policy can be set only in the app
          configuration file. -->
        <publisherPolicy apply="no" />
      </dependentAssembly>
    </assemblyBinding>
  </runtime>
</configuration>
```

### <a name="limiting-assembly--bindings-to-a-specific-version"></a><span data-ttu-id="bba74-169">특정 버전에 대한 어셈블리 바인딩 제한</span><span class="sxs-lookup"><span data-stu-id="bba74-169">Limiting assembly  bindings to a specific version</span></span>
 <span data-ttu-id="bba74-170">앱 구성 파일의 요소에 대 한 **appliesTo** 특성을 사용 [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) 하 여 .NET Framework의 특정 버전에 대 한 어셈블리 바인딩 참조를 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-170">You can use the **appliesTo** attribute on the [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) element in an app configuration file to redirect assembly binding references to a specific version of the .NET Framework.</span></span> <span data-ttu-id="bba74-171">이 선택적 특성은 .NET Framework 버전 번호를 사용하여 특성이 적용되는 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-171">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="bba74-172">**AppliesTo** 특성이 지정 되지 않은 경우 요소는 [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) .NET Framework 모든 버전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-172">If no **appliesTo** attribute is specified, the [\<assemblyBinding>](./file-schema/runtime/assemblybinding-element-for-runtime.md) element applies to all versions of the .NET Framework.</span></span>

 <span data-ttu-id="bba74-173">예를 들어 .NET Framework 버전 3.5 어셈블리에 대한 어셈블리 바인딩을 리디렉션하려면 앱 구성 파일에 다음 XML 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-173">For example, to redirect assembly binding for a .NET Framework 3.5 assembly, you would include the following XML code in your app configuration file.</span></span>

```xml
<runtime>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1"
    appliesTo="v3.5">
    <dependentAssembly>
      <!-- assembly information goes here -->
    </dependentAssembly>
  </assemblyBinding>
</runtime>
```

 <span data-ttu-id="bba74-174">버전 순서대로 리디렉션 정보를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-174">You should enter redirection information in version order.</span></span> <span data-ttu-id="bba74-175">예를 들어, .NET Framework 3.5 어셈블리에 대한 어셈블리 바인딩 리디렉션 정보를 입력한 후에 .NET Framework 4.5 어셈블리에 대한 해당 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-175">For example, enter assembly binding redirection information for .NET Framework 3.5 assemblies followed by .NET Framework 4.5 assemblies.</span></span> <span data-ttu-id="bba74-176">마지막으로 **appliesTo** 특성을 사용하지 않으므로 모든 .NET Framework 버전에 적용되는 .NET Framework 어셈블리 리디렉션에 대한 어셈블리 바인딩 리디렉션 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-176">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="bba74-177">리디렉션 시 충돌이 발생하면 구성 파일에서 일치하는 첫 번째 리디렉션 문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-177">If there is a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>

 <span data-ttu-id="bba74-178">예를 들어 한 참조를 .NET Framework 버전 3.5 어셈블리로 리디렉션하고 다른 참조를 .NET Framework 버전 4 어셈블리로 리디렉션하려면 다음 의사 코드에 표시된 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bba74-178">For example, to redirect one reference to a .NET Framework 3.5 assembly and another reference to a .NET Framework 4 assembly, use the pattern shown in the following pseudocode.</span></span>

```xml
<assemblyBinding xmlns="..." appliesTo="v3.5 ">
  <!--.NET Framework version 3.5 redirects here -->
</assemblyBinding>

<assemblyBinding xmlns="..." appliesTo="v4.0.30319">
  <!--.NET Framework version 4.0 redirects here -->
</assemblyBinding>

<assemblyBinding xmlns="...">
  <!-- redirects meant for all versions of the runtime -->
</assemblyBinding>
```

## <a name="see-also"></a><span data-ttu-id="bba74-179">추가 정보</span><span class="sxs-lookup"><span data-stu-id="bba74-179">See also</span></span>

- [<span data-ttu-id="bba74-180">방법: 자동 바인딩 리디렉션 사용 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="bba74-180">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="bba74-181">\<bindingRedirect> 요소</span><span class="sxs-lookup"><span data-stu-id="bba74-181">\<bindingRedirect> Element</span></span>](./file-schema/runtime/bindingredirect-element.md)
- [<span data-ttu-id="bba74-182">어셈블리 바인딩 리디렉션 보안 권한</span><span class="sxs-lookup"><span data-stu-id="bba74-182">Assembly Binding Redirection Security Permission</span></span>](assembly-binding-redirection-security-permission.md)
- [<span data-ttu-id="bba74-183">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="bba74-183">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="bba74-184">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="bba74-184">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="bba74-185">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="bba74-185">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="bba74-186">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="bba74-186">Configuring Apps</span></span>](index.md)
- [<span data-ttu-id="bba74-187">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bba74-187">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="bba74-188">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bba74-188">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="bba74-189">방법: 게시자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="bba74-189">How to: Create a Publisher Policy</span></span>](how-to-create-a-publisher-policy.md)
