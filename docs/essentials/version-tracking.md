---
title: 'Xamarin.Essentials: 버전 추적'
description: Xamarin.Essentials의 VersionTracking 클래스를 사용하면 응용 프로그램 버전 및 빌드 번호를 확인하고 응용 프로그램의 처음 시작되었는지 여부와 같은 추가 정보를 확인할 수 있고 현재 버전의 경우 이전 빌드 정보를 가져올 수 있습니다.
ms.assetid: 670C7E8A-E882-4AC0-97D2-A53D90ADD6A3
author: jamesmontemagno
ms.author: jamont
ms.date: 11/04/2018
ms.openlocfilehash: 7d3877577523ed17c78fd5d2ad02923bd3d821e2
ms.sourcegitcommit: 01f93a34b466f8d4043cef68fab9b35cd8decee6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2018
ms.locfileid: "52898840"
---
# <a name="xamarinessentials-version-tracking"></a>Xamarin.Essentials: 버전 추적

**VersionTracking** 클래스를 사용하면 응용 프로그램 버전 및 빌드 번호를 확인하고 응용 프로그램의 처음 시작되었는지 여부와 같은 추가 정보를 확인할 수 있고 현재 버전의 경우 이전 빌드 정보를 가져올 수 있습니다.

## <a name="get-started"></a>시작

[!include[](~/essentials/includes/get-started.md)]

## <a name="using-version-tracking"></a>버전 추적 사용

클래스에서 Xamarin.Essentials에 대한 참조를 추가합니다.

```csharp
using Xamarin.Essentials;
```

**VersionTracking** 클래스를 처음 사용하면 현재 버전이 추적됩니다. 현재 버전 정보가 추적되는지 확인하려면 로드될 때마다 응용 프로그램에서만 초기에 `Track`을 호출해야 합니다.

```csharp
VersionTracking.Track();
```

초기 `Track`이 호출된 후 버전 정보를 읽을 수 있습니다.

```csharp

// First time ever launched application
var firstLaunch = VersionTracking.IsFirstLaunchEver;

// First time launching current version
var firstLaunchCurrent = VersionTracking.IsFirstLaunchForCurrentVersion;

// First time launching current build
var firstLaunchBuild = VersionTracking.IsFirstLaunchForCurrentBuild;

// Current app version (2.0.0)
var currentVersion = VersionTracking.CurrentVersion;

// Current build (2)
var currentBuild = VersionTracking.CurrentBuild;

// Previous app version (1.0.0)
var previousVersion = VersionTracking.PreviousVersion;

// Previous app build (1)
var previousBuild = VersionTracking.PreviousBuild;

// First version of app installed (1.0.0)
var firstVersion = VersionTracking.FirstInstalledVersion;

// First build of app installed (1)
var firstBuild = VersionTracking.FirstInstalledBuild;

// List of versions installed (1.0.0, 2.0.0)
var versionHistory = VersionTracking.VersionHistory;

// List of builds installed (1, 2)
var buildHistory = VersionTracking.BuildHistory;
```

## <a name="platform-implementation-specifics"></a>플랫폼 구현 관련 정보

모든 버전 정보는 Xamarin.Essentials의 [기본 설정](preferences.md) API를 사용하여 저장되며 파일 이름 **[YOUR-APP-PACKAGE-ID].xamarinessentials.versiontracking**으로 저장되고 [기본 설정](preferences.md#persistence) 문서에 설명된 동일한 데이터 지속성을 따릅니다.

## <a name="api"></a>API

- [버전 추적 소스 코드](https://github.com/xamarin/Essentials/tree/master/Xamarin.Essentials/VersionTracking)
- [버전 추적 API 문서](xref:Xamarin.Essentials.VersionTracking)
