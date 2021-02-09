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

export default {
    created: function() {        
      var culture = "de";
      ResourceManager.setLocalizationMessages(require(`../json resources/dx-dashboard.${culture}.json`));
      ResourceManager.setLocalizationMessages(require(`../json resources/dx-analytics-core.${culture}.json`));
  
      // Apply culture-specific formatting:
      locale(culture);  
  
      // Localize the specified string at runtime (the "Export To" button's caption in the dashboard title):
      ResourceManager.setLocalizationMessages({ "DashboardStringId.ActionExportTo": "Custom Text for Export Button" });  
    },
    components: {
        DxDashboardControl
    }
}
</script>