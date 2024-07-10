# BCAppInsights

This repository contains the events (signals) that are sent from BC to Application Insights

This repository must remain public so that the Azure Data Explorer Dashboards can include it in the base queries
e.g.

let SignalDefinitions = externaldata(eventId :string, eventArea:string, eventDescription:string)
        [h@'https://raw.githubusercontent.com/Gisela-Graham-Limited/BCAppInsights/main/events.json']
            with(format='multijson')
    | where eventId has_any (_eventId); //Filter as soon as possible
