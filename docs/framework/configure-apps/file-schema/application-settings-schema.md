---
title: 응용 프로그램 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 90d471888950347c041b4824b659ce33fda512d7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242831"
---
# <a name="application-settings-schema"></a><span data-ttu-id="7d9ff-102">응용 프로그램 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7d9ff-102">Application Settings schema</span></span>

<span data-ttu-id="7d9ff-103">응용 프로그램 설정을 사용하면 Windows Forms 또는 ASP.NET 응용 프로그램이 응용 프로그램 범위 및 사용자 범위 설정을 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="7d9ff-104">이 컨텍스트에서 *설정은* 응용 프로그램에 특정하거나 현재 사용자에 특정할 수 있는 모든 정보(데이터베이스 연결 문자열에서 사용자의 기본 기본 창 크기에 이르기까지)입니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="7d9ff-105">기본적으로 Windows Forms 응용 프로그램의 응용 <xref:System.Configuration.LocalFileSettingsProvider> 프로그램 설정은 .NET 구성 시스템을 사용하여 XML 구성 파일에 설정을 저장하는 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="7d9ff-106">응용 프로그램 설정에서 사용되는 파일에 대한 자세한 내용은 [응용 프로그램 설정 아키텍처](../../winforms/advanced/application-settings-architecture.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="7d9ff-107">응용 프로그램 설정은 다음 요소를 사용하는 구성 파일의 일부로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="7d9ff-108">요소</span><span class="sxs-lookup"><span data-stu-id="7d9ff-108">Element</span></span>                    | <span data-ttu-id="7d9ff-109">Description</span><span class="sxs-lookup"><span data-stu-id="7d9ff-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="7d9ff-110">**\<응용 프로그램설정>**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="7d9ff-111">응용 프로그램에 \*\* \<특정한\*\* 모든 설정>태그를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="7d9ff-112">**\<사용자 설정>**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-112">**\<userSettings>**</span></span>        | <span data-ttu-id="7d9ff-113">현재 \*\* \<\*\* 사용자와 관련된 모든 설정>태그를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="7d9ff-114">**\<>설정**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-114">**\<setting>**</span></span>             | <span data-ttu-id="7d9ff-115">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-115">Defines a setting.</span></span> <span data-ttu-id="7d9ff-116">응용 프로그램의 하위>또는 \*\* \<\*\* \*\* \<사용자설정>\*\*.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="7d9ff-117">**\<값>**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-117">**\<value>**</span></span>               | <span data-ttu-id="7d9ff-118">설정 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-118">Defines a setting's value.</span></span> <span data-ttu-id="7d9ff-119">설정의 자식>. \*\* \< \*\*</span><span class="sxs-lookup"><span data-stu-id="7d9ff-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="7d9ff-120">\<응용 프로그램설정> 요소</span><span class="sxs-lookup"><span data-stu-id="7d9ff-120">\<applicationSettings> element</span></span>

<span data-ttu-id="7d9ff-121">이 요소에는 \*\* \<\*\* 클라이언트 컴퓨터에서 응용 프로그램의 인스턴스와 관련된 모든 설정>태그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="7d9ff-122">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="7d9ff-123">\<사용자 설정> 요소</span><span class="sxs-lookup"><span data-stu-id="7d9ff-123">\<userSettings> element</span></span>

<span data-ttu-id="7d9ff-124">이 요소에는 \*\* \<\*\* 현재 응용 프로그램을 사용하는 사용자와 관련된 모든 설정>태그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="7d9ff-125">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="7d9ff-126">\<> 요소 설정</span><span class="sxs-lookup"><span data-stu-id="7d9ff-126">\<setting> element</span></span>

<span data-ttu-id="7d9ff-127">이 요소는 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-127">This element defines a setting.</span></span> <span data-ttu-id="7d9ff-128">다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-128">It has the following attributes.</span></span>

| <span data-ttu-id="7d9ff-129">attribute</span><span class="sxs-lookup"><span data-stu-id="7d9ff-129">Attribute</span></span>        | <span data-ttu-id="7d9ff-130">Description</span><span class="sxs-lookup"><span data-stu-id="7d9ff-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="7d9ff-131">**(이름)**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-131">**name**</span></span>         | <span data-ttu-id="7d9ff-132">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-132">Required.</span></span> <span data-ttu-id="7d9ff-133">설정의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-133">The unique ID of the setting.</span></span> <span data-ttu-id="7d9ff-134">Visual Studio를 통해 만든 설정은 이름으로 `ProjectName.Properties.Settings`저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="7d9ff-135">**직렬화**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-135">**serializeAs**</span></span> | <span data-ttu-id="7d9ff-136">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-136">Required.</span></span> <span data-ttu-id="7d9ff-137">값을 텍스트로 직렬화하는 데 사용할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="7d9ff-138">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-138">Valid values are:</span></span><br><br><span data-ttu-id="7d9ff-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-139">- `string`.</span></span> <span data-ttu-id="7d9ff-140">값은 <xref:System.ComponentModel.TypeConverter>을 사용하여 문자열로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="7d9ff-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-141">- `xml`.</span></span> <span data-ttu-id="7d9ff-142">값은 XML 직렬화를 사용하여 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="7d9ff-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-143">- `binary`.</span></span> <span data-ttu-id="7d9ff-144">이중 직렬화를 사용하여 텍스트 인코딩된 바이너리로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="7d9ff-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-145">- `custom`.</span></span> <span data-ttu-id="7d9ff-146">설정 공급자는 이 설정에 대한 고유한 지식을 가지고 있으며 직렬화하고 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="7d9ff-147">\<값> 요소</span><span class="sxs-lookup"><span data-stu-id="7d9ff-147">\<value> element</span></span>

<span data-ttu-id="7d9ff-148">이 요소에는 설정 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="7d9ff-149">예제</span><span class="sxs-lookup"><span data-stu-id="7d9ff-149">Example</span></span>

<span data-ttu-id="7d9ff-150">다음 예제에서는 두 개의 응용 프로그램 범위 설정과 두 개의 사용자 범위 설정을 정의하는 응용 프로그램 설정 파일을 보여 주십니다.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7d9ff-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d9ff-151">See also</span></span>

- [<span data-ttu-id="7d9ff-152">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="7d9ff-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="7d9ff-153">애플리케이션 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="7d9ff-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
