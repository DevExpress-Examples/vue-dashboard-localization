<template>
    <div>
        <DxDashboardControl 
            style="height:900px; display: 'block'; width: '100%';"
            endpoint="http://localhost:5000/api/dashboard"
        />
    </div>  
</template>

<script>
import { DxDashboardControl } from 'devexpress-dashboard-vue';
import { ResourceManager } from 'devexpress-dashboard';
import { locale } from "devextreme/localization";
import deAnalyticsMessages from '../jsonResources/dx-analytics-core.de.json';
import deDashboardMessages from '../jsonResources/dx-dashboard.de.json';

export default {
    created: function() {    
        // Localize the Web Dashboard UI for the German market (the 'de' culture):
        ResourceManager.setLocalizationMessages(deAnalyticsMessages);
        ResourceManager.setLocalizationMessages(deDashboardMessages);
        
        // Apply culture-specific formatting:
        locale('de');  
        
        // Localize the specified string at runtime (the "Export To" button's caption in the dashboard title):
        ResourceManager.setLocalizationMessages({ "DashboardStringId.ActionExportTo": "Custom Text for Export Button" });
    },
    components: {
        DxDashboardControl
    }
}
</script>