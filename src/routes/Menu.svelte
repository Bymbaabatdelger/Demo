<script lang="ts">
    let { name, icon } = $props();
    </script>
    
    <div>
        <img src={icon} alt="" />
        <p>{name}</p>
    </div>
    
    <style>
        div {
            display: flex;
            gap: 10px;
            align-items: center;
        }
    
        p {
            color: #A1A1AA;
            font-size: 16px;
            font-family: 'Roboto', sans-serif;
        }
    
        img {
            height: 20px;
            width: 20px;
            transition: filter 0.3s ease; 
        }
        div:hover p {
            color: white; 
        }
        div:hover img {
            filter: brightness(0) saturate(100%) invert(1); 
        }
    </style>
    